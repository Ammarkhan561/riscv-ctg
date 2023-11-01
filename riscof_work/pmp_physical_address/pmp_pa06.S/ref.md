
# Data Propagation Report

- **STAT1** : Number of instructions that hit unique coverpoints and update the signature
- **STAT2** : Number of instructions that hit covepoints which are not unique but still update the signature (completely or partially)
- **STAT3** : Number of instructions that hit a unique coverpoint but do not update the signature completely
- **STAT4** : Number of multiple signature updates for the same coverpoint
- **STAT5** : Number of times the signature was overwritten

| Param                     | Value    |
|---------------------------|----------|
| XLEN                      | 64      |
| TEST_REGION               | []      |
| SIG_REGION                | [('0x80000000007110', '0x80000000007320', '66 dwords')]      |
| COV_LABELS                | pmp_pa06      |
| TEST_NAME                 | /home/ammar/Documents/my-github/riscv-ctg/riscof_work/pmp_physical_address/pmp_pa06.S/ref.S    |
| Total Number of coverpoints| 12     |
| Total Coverpoints Hit     | 12      |
| Total Signature Updates   | 15      |
| STAT1                     | 0      |
| STAT2                     | 15      |
| STAT3                     | 11     |
| STAT4                     | 0     |
| STAT5                     | 0     |

## Details for STAT2:

```
Op without unique coverpoint updates Signature
 -- Code Sequence:
      [0x80000000000698]:sd a4, 0(a3)
 -- Signature Addresses:
      Address: 0x80000000007118 Data: 0x000000000000CEED
 -- Redundant Coverpoints hit by the op
      - mnemonic : sd




Op without unique coverpoint updates Signature
 -- Code Sequence:
      [0x800000000006a4]:sd a4, 8(a3)
 -- Signature Addresses:
      Address: 0x80000000007120 Data: 0x000000000000BEED
 -- Redundant Coverpoints hit by the op
      - mnemonic : sd




Op without unique coverpoint updates Signature
 -- Code Sequence:
      [0x80000000000ff4]:sd a1, 0(t1)
 -- Signature Addresses:
      Address: 0x80000000007218 Data: 0x00000000000010E3
 -- Redundant Coverpoints hit by the op
      - mnemonic : sd




Op without unique coverpoint updates Signature
 -- Code Sequence:
      [0x80000000000f64]:csrrs a0, mcause, zero
      [0x80000000000f68]:addi s1, a0, 4088
      [0x80000000000f6c]:andi s1, s1, 4092
      [0x80000000000f70]:bne s1, zero, 12
      [0x80000000000f7c]:addi t2, zero, 32
      [0x80000000000f80]:bge a0, zero, 68
      [0x80000000000fc4]:csrrs t1, misa, zero
      [0x80000000000fc8]:slli t1, t1, 56
      [0x80000000000fcc]:bge t1, zero, 8
      [0x80000000000fd4]:ld t1, 536(sp)
      [0x80000000000fd8]:add s1, t1, t2
      [0x80000000000fdc]:sd s1, 536(sp)
      [0x80000000000fe0]:ld fp, 576(sp)
      [0x80000000000fe4]:sub a1, a1, fp
      [0x80000000000fe8]:slli a1, a1, 4
      [0x80000000000fec]:or a1, a1, t2
      [0x80000000000ff0]:addi a1, a1, 3
      [0x80000000000ff4]:sd a1, 0(t1)
      [0x80000000000ff8]:sd a0, 8(t1)
 -- Signature Addresses:
      Address: 0x80000000007220 Data: 0x0000000000000001
 -- Redundant Coverpoints hit by the op
      - mnemonic : csrrs




Op without unique coverpoint updates Signature
 -- Code Sequence:
      [0x8000000000103c]:ld fp, 472(s1)
      [0x80000000001040]:ld a1, 480(s1)
      [0x80000000001044]:add a1, a1, fp
      [0x80000000001048]:bgeu t2, a1, 8
      [0x8000000000104c]:bgeu t2, fp, 24
      [0x80000000001064]:sub fp, t2, fp
      [0x80000000001068]:sd fp, 16(t1)
 -- Signature Addresses:
      Address: 0x80000000007228 Data: 0x00000000000005A8
 -- Redundant Coverpoints hit by the op
      - mnemonic : ld




Op without unique coverpoint updates Signature
 -- Code Sequence:
      [0x800000000010d4]:ld fp, 472(s1)
      [0x800000000010d8]:ld a1, 480(s1)
      [0x800000000010dc]:add a1, a1, fp
      [0x800000000010e0]:bgeu t2, a1, 8
      [0x800000000010e4]:bgeu t2, fp, 24
      [0x800000000010fc]:sub fp, t2, fp
      [0x80000000001100]:sd fp, 24(t1)
 -- Signature Addresses:
      Address: 0x80000000007230 Data: 0x00000000000005A8
 -- Redundant Coverpoints hit by the op
      - mnemonic : ld




Op without unique coverpoint updates Signature
 -- Code Sequence:
      [0x80000000001134]:ld a1, 648(sp)
      [0x80000000001138]:ld sp, 656(sp)
      [0x8000000000113c]:mret
      [0x900000bf4]:lui a4, 0
      [0x900000bf8]:addi a4, a4, 0
      [0x900000bfc]:slli a4, a4, 11
      [0x900000c00]:addi a4, a4, 0
      [0x900000c04]:slli a4, a4, 11
      [0x900000c08]:addi a4, a4, 55
      [0x900000c0c]:slli a4, a4, 10
      [0x900000c10]:addi a4, a4, 685
      [0x900000c14]:sd a4, 16(s11)
      [0x900000c18]:addi zero, zero, 0
      [0x900000c1c]:lui t0, 0
      [0x900000c20]:addi t0, t0, 9
      [0x900000c24]:slli t0, t0, 11
      [0x900000c28]:addi t0, t0, 1024
      [0x900000c2c]:slli t0, t0, 11
      [0x900000c30]:addi t0, t0, 1
      [0x900000c34]:slli t0, t0, 10
      [0x900000c38]:addi t0, t0, 648
      [0x900000c3c]:ld t0, 0(t0)
      [0x80000000000d80]:jal zero, 256
      [0x80000000000e80]:csrrw sp, mscratch, sp
      [0x80000000000e84]:sd a1, 648(sp)
      [0x80000000000e88]:jal a1, 184
      [0x80000000000f40]:sd a0, 640(sp)
      [0x80000000000f44]:csrrw a0, mscratch, sp
      [0x80000000000f48]:sd a0, 656(sp)
      [0x80000000000f4c]:ld a0, 560(sp)
      [0x80000000000f50]:jalr zero, a0, 0
      [0x80000000000f54]:sd s1, 632(sp)
      [0x80000000000f58]:sd fp, 624(sp)
      [0x80000000000f5c]:sd t2, 616(sp)
      [0x80000000000f60]:sd t1, 608(sp)
      [0x80000000000f64]:csrrs a0, mcause, zero
      [0x80000000000f68]:addi s1, a0, 4088
      [0x80000000000f6c]:andi s1, s1, 4092
      [0x80000000000f70]:bne s1, zero, 12
      [0x80000000000f7c]:addi t2, zero, 32
      [0x80000000000f80]:bge a0, zero, 68
      [0x80000000000fc4]:csrrs t1, misa, zero
      [0x80000000000fc8]:slli t1, t1, 56
      [0x80000000000fcc]:bge t1, zero, 8
      [0x80000000000fd4]:ld t1, 536(sp)
      [0x80000000000fd8]:add s1, t1, t2
      [0x80000000000fdc]:sd s1, 536(sp)
      [0x80000000000fe0]:ld fp, 576(sp)
      [0x80000000000fe4]:sub a1, a1, fp
      [0x80000000000fe8]:slli a1, a1, 4
      [0x80000000000fec]:or a1, a1, t2
      [0x80000000000ff0]:addi a1, a1, 3
      [0x80000000000ff4]:sd a1, 0(t1)
 -- Signature Addresses:
      Address: 0x80000000007238 Data: 0x00000000000010E3
 -- Redundant Coverpoints hit by the op
      - mnemonic : ld




Op without unique coverpoint updates Signature
 -- Code Sequence:
      [0x80000000000f64]:csrrs a0, mcause, zero
      [0x80000000000f68]:addi s1, a0, 4088
      [0x80000000000f6c]:andi s1, s1, 4092
      [0x80000000000f70]:bne s1, zero, 12
      [0x80000000000f7c]:addi t2, zero, 32
      [0x80000000000f80]:bge a0, zero, 68
      [0x80000000000fc4]:csrrs t1, misa, zero
      [0x80000000000fc8]:slli t1, t1, 56
      [0x80000000000fcc]:bge t1, zero, 8
      [0x80000000000fd4]:ld t1, 536(sp)
      [0x80000000000fd8]:add s1, t1, t2
      [0x80000000000fdc]:sd s1, 536(sp)
      [0x80000000000fe0]:ld fp, 576(sp)
      [0x80000000000fe4]:sub a1, a1, fp
      [0x80000000000fe8]:slli a1, a1, 4
      [0x80000000000fec]:or a1, a1, t2
      [0x80000000000ff0]:addi a1, a1, 3
      [0x80000000000ff4]:sd a1, 0(t1)
      [0x80000000000ff8]:sd a0, 8(t1)
 -- Signature Addresses:
      Address: 0x80000000007240 Data: 0x0000000000000005
 -- Redundant Coverpoints hit by the op
      - mnemonic : csrrs




Op without unique coverpoint updates Signature
 -- Code Sequence:
      [0x8000000000103c]:ld fp, 472(s1)
      [0x80000000001040]:ld a1, 480(s1)
      [0x80000000001044]:add a1, a1, fp
      [0x80000000001048]:bgeu t2, a1, 8
      [0x8000000000104c]:bgeu t2, fp, 24
      [0x80000000001064]:sub fp, t2, fp
      [0x80000000001068]:sd fp, 16(t1)
 -- Signature Addresses:
      Address: 0x80000000007248 Data: 0x00000000000005F8
 -- Redundant Coverpoints hit by the op
      - mnemonic : ld




Op without unique coverpoint updates Signature
 -- Code Sequence:
      [0x800000000010ac]:ld fp, 520(s1)
      [0x800000000010b0]:ld a1, 528(s1)
      [0x800000000010b4]:add a1, a1, fp
      [0x800000000010b8]:bgeu t2, a1, 8
      [0x800000000010bc]:bgeu t2, fp, 64
      [0x800000000010fc]:sub fp, t2, fp
      [0x80000000001100]:sd fp, 24(t1)
 -- Signature Addresses:
      Address: 0x80000000007250 Data: 0x0000000000000044
 -- Redundant Coverpoints hit by the op
      - mnemonic : ld




Op without unique coverpoint updates Signature
 -- Code Sequence:
      [0x80000000001134]:ld a1, 648(sp)
      [0x80000000001138]:ld sp, 656(sp)
      [0x8000000000113c]:mret
      [0x900000c44]:sd sp, 0(t0)
      [0x80000000000d80]:jal zero, 256
      [0x80000000000e80]:csrrw sp, mscratch, sp
      [0x80000000000e84]:sd a1, 648(sp)
      [0x80000000000e88]:jal a1, 184
      [0x80000000000f40]:sd a0, 640(sp)
      [0x80000000000f44]:csrrw a0, mscratch, sp
      [0x80000000000f48]:sd a0, 656(sp)
      [0x80000000000f4c]:ld a0, 560(sp)
      [0x80000000000f50]:jalr zero, a0, 0
      [0x80000000000f54]:sd s1, 632(sp)
      [0x80000000000f58]:sd fp, 624(sp)
      [0x80000000000f5c]:sd t2, 616(sp)
      [0x80000000000f60]:sd t1, 608(sp)
      [0x80000000000f64]:csrrs a0, mcause, zero
      [0x80000000000f68]:addi s1, a0, 4088
      [0x80000000000f6c]:andi s1, s1, 4092
      [0x80000000000f70]:bne s1, zero, 12
      [0x80000000000f7c]:addi t2, zero, 32
      [0x80000000000f80]:bge a0, zero, 68
      [0x80000000000fc4]:csrrs t1, misa, zero
      [0x80000000000fc8]:slli t1, t1, 56
      [0x80000000000fcc]:bge t1, zero, 8
      [0x80000000000fd4]:ld t1, 536(sp)
      [0x80000000000fd8]:add s1, t1, t2
      [0x80000000000fdc]:sd s1, 536(sp)
      [0x80000000000fe0]:ld fp, 576(sp)
      [0x80000000000fe4]:sub a1, a1, fp
      [0x80000000000fe8]:slli a1, a1, 4
      [0x80000000000fec]:or a1, a1, t2
      [0x80000000000ff0]:addi a1, a1, 3
      [0x80000000000ff4]:sd a1, 0(t1)
 -- Signature Addresses:
      Address: 0x80000000007258 Data: 0x00000000000010E3
 -- Redundant Coverpoints hit by the op
      - mnemonic : ld




Op without unique coverpoint updates Signature
 -- Code Sequence:
      [0x80000000000f64]:csrrs a0, mcause, zero
      [0x80000000000f68]:addi s1, a0, 4088
      [0x80000000000f6c]:andi s1, s1, 4092
      [0x80000000000f70]:bne s1, zero, 12
      [0x80000000000f7c]:addi t2, zero, 32
      [0x80000000000f80]:bge a0, zero, 68
      [0x80000000000fc4]:csrrs t1, misa, zero
      [0x80000000000fc8]:slli t1, t1, 56
      [0x80000000000fcc]:bge t1, zero, 8
      [0x80000000000fd4]:ld t1, 536(sp)
      [0x80000000000fd8]:add s1, t1, t2
      [0x80000000000fdc]:sd s1, 536(sp)
      [0x80000000000fe0]:ld fp, 576(sp)
      [0x80000000000fe4]:sub a1, a1, fp
      [0x80000000000fe8]:slli a1, a1, 4
      [0x80000000000fec]:or a1, a1, t2
      [0x80000000000ff0]:addi a1, a1, 3
      [0x80000000000ff4]:sd a1, 0(t1)
      [0x80000000000ff8]:sd a0, 8(t1)
 -- Signature Addresses:
      Address: 0x80000000007260 Data: 0x0000000000000007
 -- Redundant Coverpoints hit by the op
      - mnemonic : csrrs




Op without unique coverpoint updates Signature
 -- Code Sequence:
      [0x8000000000103c]:ld fp, 472(s1)
      [0x80000000001040]:ld a1, 480(s1)
      [0x80000000001044]:add a1, a1, fp
      [0x80000000001048]:bgeu t2, a1, 8
      [0x8000000000104c]:bgeu t2, fp, 24
      [0x80000000001064]:sub fp, t2, fp
      [0x80000000001068]:sd fp, 16(t1)
 -- Signature Addresses:
      Address: 0x80000000007268 Data: 0x0000000000000600
 -- Redundant Coverpoints hit by the op
      - mnemonic : ld




Op without unique coverpoint updates Signature
 -- Code Sequence:
      [0x800000000010ac]:ld fp, 520(s1)
      [0x800000000010b0]:ld a1, 528(s1)
      [0x800000000010b4]:add a1, a1, fp
      [0x800000000010b8]:bgeu t2, a1, 8
      [0x800000000010bc]:bgeu t2, fp, 64
      [0x800000000010fc]:sub fp, t2, fp
      [0x80000000001100]:sd fp, 24(t1)
 -- Signature Addresses:
      Address: 0x80000000007270 Data: 0x0000000000000044
 -- Redundant Coverpoints hit by the op
      - mnemonic : ld




Op without unique coverpoint updates Signature
 -- Code Sequence:
      [0x80000000000c84]:sd a4, 32(a3)
 -- Signature Addresses:
      Address: 0x80000000007140 Data: 0x0000000000000123
 -- Redundant Coverpoints hit by the op
      - mnemonic : sd






```

## Details of STAT3

```
[0x80000000000024]:sd fp, 592(t1)
[0x80000000000028]:addi t2, zero, 0
[0x8000000000002c]:csrrw t2, medeleg, t2

[0x1008]:csrrs a0, mhartid, zero
[0x100c]:ld t0, 24(t0)
[0x1010]:jalr zero, t0, 0
[0x80000000000000]:auipc t1, 3
[0x80000000000004]:addi t1, t1, 0
[0x80000000000008]:addi zero, zero, 0
[0x8000000000000c]:addi zero, zero, 0
[0x80000000000010]:addi zero, zero, 0
[0x80000000000014]:addi zero, zero, 0
[0x80000000000018]:addi zero, zero, 0
[0x8000000000001c]:addi zero, zero, 0
[0x80000000000020]:csrrw fp, mscratch, t1
[0x80000000000024]:sd fp, 592(t1)
[0x80000000000028]:addi t2, zero, 0
[0x8000000000002c]:csrrw t2, medeleg, t2
[0x80000000000030]:sd t2, 568(t1)
[0x80000000000034]:addi zero, zero, 0
[0x80000000000038]:addi zero, zero, 0
[0x8000000000003c]:addi zero, zero, 0
[0x80000000000040]:auipc s1, 1
[0x80000000000044]:addi s1, s1, 3392
[0x80000000000048]:addi zero, zero, 0
[0x8000000000004c]:addi zero, zero, 0
[0x80000000000050]:addi zero, zero, 0
[0x80000000000054]:addi zero, zero, 0
[0x80000000000058]:addi zero, zero, 0
[0x8000000000005c]:addi zero, zero, 0
[0x80000000000060]:addi fp, s1, 468
[0x80000000000064]:sd fp, 560(t1)
[0x80000000000068]:csrrs fp, mtvec, zero
[0x8000000000006c]:sd fp, 584(t1)
[0x80000000000070]:andi t2, fp, 3
[0x80000000000074]:or t2, s1, t2
[0x80000000000078]:sd t2, 576(t1)
[0x8000000000007c]:csrrw zero, mtvec, t2
[0x80000000000080]:csrrs a0, mtvec, zero

[0x80000000000848]:sd a0, 0(t1)
[0x8000000000084c]:addi zero, zero, 0
[0x80000000000850]:addi zero, zero, 0
[0x80000000000854]:addi zero, zero, 0
[0x80000000000858]:addi zero, zero, 0
[0x8000000000085c]:addi zero, zero, 0
[0x80000000000860]:auipc a0, 3
[0x80000000000864]:addi a0, a0, 1952
[0x80000000000868]:addi zero, zero, 0
[0x8000000000086c]:addi zero, zero, 0
[0x80000000000870]:addi zero, zero, 0
[0x80000000000874]:addi zero, zero, 0
[0x80000000000878]:addi zero, zero, 0
[0x8000000000087c]:addi zero, zero, 0
[0x80000000000880]:addi a1, zero, 1
[0x80000000000884]:srli a0, a0, 12
[0x80000000000888]:slli a0, a0, 10
[0x8000000000088c]:or a0, a0, a1
[0x80000000000890]:addi zero, zero, 0
[0x80000000000894]:addi zero, zero, 0
[0x80000000000898]:addi zero, zero, 0
[0x8000000000089c]:addi zero, zero, 0
[0x800000000008a0]:auipc t1, 5
[0x800000000008a4]:addi t1, t1, 1888
[0x800000000008a8]:addi zero, zero, 0
[0x800000000008ac]:addi zero, zero, 0
[0x800000000008b0]:addi zero, zero, 0
[0x800000000008b4]:addi zero, zero, 0
[0x800000000008b8]:addi zero, zero, 0
[0x800000000008bc]:addi zero, zero, 0
[0x800000000008c0]:addi t0, zero, 320
[0x800000000008c4]:add t1, t1, t0
[0x800000000008c8]:sd a0, 0(t1)

[0x80000000000020]:csrrw fp, mscratch, t1
[0x80000000000024]:sd fp, 592(t1)
[0x80000000000028]:addi t2, zero, 0
[0x8000000000002c]:csrrw t2, medeleg, t2
[0x80000000000030]:sd t2, 568(t1)
[0x80000000000034]:addi zero, zero, 0
[0x80000000000038]:addi zero, zero, 0
[0x8000000000003c]:addi zero, zero, 0
[0x80000000000040]:auipc s1, 1
[0x80000000000044]:addi s1, s1, 3392
[0x80000000000048]:addi zero, zero, 0
[0x8000000000004c]:addi zero, zero, 0
[0x80000000000050]:addi zero, zero, 0
[0x80000000000054]:addi zero, zero, 0
[0x80000000000058]:addi zero, zero, 0
[0x8000000000005c]:addi zero, zero, 0
[0x80000000000060]:addi fp, s1, 468
[0x80000000000064]:sd fp, 560(t1)
[0x80000000000068]:csrrs fp, mtvec, zero
[0x8000000000006c]:sd fp, 584(t1)
[0x80000000000070]:andi t2, fp, 3
[0x80000000000074]:or t2, s1, t2
[0x80000000000078]:sd t2, 576(t1)
[0x8000000000007c]:csrrw zero, mtvec, t2
[0x80000000000080]:csrrs a0, mtvec, zero
[0x80000000000084]:beq a0, t2, 128
[0x80000000000104]:addi zero, zero, 0
[0x80000000000108]:addi zero, zero, 0
[0x8000000000010c]:addi zero, zero, 0
[0x80000000000110]:addi zero, zero, 0
[0x80000000000114]:addi zero, zero, 0
[0x80000000000118]:addi zero, zero, 0
[0x8000000000011c]:addi zero, zero, 0
[0x80000000000120]:auipc t1, 3
[0x80000000000124]:addi t1, t1, 376
[0x80000000000128]:addi zero, zero, 0
[0x8000000000012c]:addi zero, zero, 0
[0x80000000000130]:addi zero, zero, 0
[0x80000000000134]:addi zero, zero, 0
[0x80000000000138]:addi zero, zero, 0
[0x8000000000013c]:addi zero, zero, 0
[0x80000000000140]:csrrw fp, sscratch, t1
[0x80000000000144]:sd fp, 592(t1)
[0x80000000000148]:addi t2, zero, 0
[0x8000000000014c]:sd t2, 568(t1)
[0x80000000000150]:addi zero, zero, 0
[0x80000000000154]:addi zero, zero, 0
[0x80000000000158]:addi zero, zero, 0
[0x8000000000015c]:addi zero, zero, 0
[0x80000000000160]:auipc s1, 6
[0x80000000000164]:addi s1, s1, 3744
[0x80000000000168]:addi zero, zero, 0
[0x8000000000016c]:addi zero, zero, 0
[0x80000000000170]:addi zero, zero, 0
[0x80000000000174]:addi zero, zero, 0
[0x80000000000178]:addi zero, zero, 0
[0x8000000000017c]:addi zero, zero, 0
[0x80000000000180]:csrrw s1, satp, s1
[0x80000000000184]:sd s1, 544(t1)
[0x80000000000188]:addi zero, zero, 0
[0x8000000000018c]:addi zero, zero, 0
[0x80000000000190]:addi zero, zero, 0
[0x80000000000194]:addi zero, zero, 0
[0x80000000000198]:addi zero, zero, 0
[0x8000000000019c]:addi zero, zero, 0
[0x800000000001a0]:auipc s1, 1
[0x800000000001a4]:addi s1, s1, 1184
[0x800000000001a8]:addi zero, zero, 0
[0x800000000001ac]:addi zero, zero, 0
[0x800000000001b0]:addi zero, zero, 0
[0x800000000001b4]:addi zero, zero, 0
[0x800000000001b8]:addi zero, zero, 0
[0x800000000001bc]:addi zero, zero, 0
[0x800000000001c0]:addi fp, s1, 468
[0x800000000001c4]:sd fp, 560(t1)
[0x800000000001c8]:csrrs fp, stvec, zero
[0x800000000001cc]:sd fp, 584(t1)
[0x800000000001d0]:andi t2, fp, 3
[0x800000000001d4]:or t2, s1, t2
[0x800000000001d8]:sd t2, 576(t1)
[0x800000000001dc]:csrrw zero, stvec, t2
[0x800000000001e0]:csrrs a0, stvec, zero
[0x800000000001e4]:beq a0, t2, 128
[0x80000000000264]:lui ra, 1044188
[0x80000000000268]:addi ra, ra, 3757
[0x8000000000026c]:slli ra, ra, 11
[0x80000000000270]:addi ra, ra, 2039
[0x80000000000274]:slli ra, ra, 11
[0x80000000000278]:addi ra, ra, 879
[0x8000000000027c]:slli ra, ra, 10
[0x80000000000280]:addi ra, ra, 685
[0x80000000000284]:lui sp, 1046382
[0x80000000000288]:addi sp, sp, 3926
[0x8000000000028c]:slli sp, sp, 11
[0x80000000000290]:addi sp, sp, 2043
[0x80000000000294]:slli sp, sp, 11
[0x80000000000298]:addi sp, sp, 1463
[0x8000000000029c]:slli sp, sp, 10
[0x800000000002a0]:addi sp, sp, 854
[0x800000000002a4]:lui gp, 523191
[0x800000000002a8]:addi gp, gp, 4011
[0x800000000002ac]:slli gp, gp, 11
[0x800000000002b0]:addi gp, gp, 1021
[0x800000000002b4]:slli gp, gp, 11
[0x800000000002b8]:addi gp, gp, 1755
[0x800000000002bc]:slli gp, gp, 10
[0x800000000002c0]:addi gp, gp, 939
[0x800000000002c4]:lui tp, 785883
[0x800000000002c8]:addi tp, tp, 2005
[0x800000000002cc]:slli tp, tp, 11
[0x800000000002d0]:addi tp, tp, 1534
[0x800000000002d4]:slli tp, tp, 11
[0x800000000002d8]:addi tp, tp, 1901
[0x800000000002dc]:slli tp, tp, 10
[0x800000000002e0]:addi tp, tp, 981
[0x800000000002e4]:lui t0, 917230
[0x800000000002e8]:addi t0, t0, 3050
[0x800000000002ec]:slli t0, t0, 11
[0x800000000002f0]:addi t0, t0, 1791
[0x800000000002f4]:slli t0, t0, 11
[0x800000000002f8]:addi t0, t0, 950
[0x800000000002fc]:slli t0, t0, 10
[0x80000000000300]:addi t0, t0, 1002
[0x80000000000304]:lui t1, 458615
[0x80000000000308]:addi t1, t1, 3573
[0x8000000000030c]:slli t1, t1, 11
[0x80000000000310]:addi t1, t1, 895
[0x80000000000314]:slli t1, t1, 11
[0x80000000000318]:addi t1, t1, 1499
[0x8000000000031c]:slli t1, t1, 10
[0x80000000000320]:addi t1, t1, 501
[0x80000000000324]:lui t2, 753595
[0x80000000000328]:addi t2, t2, 1786
[0x8000000000032c]:slli t2, t2, 11
[0x80000000000330]:addi t2, t2, 1471
[0x80000000000334]:slli t2, t2, 11
[0x80000000000338]:addi t2, t2, 1773
[0x8000000000033c]:slli t2, t2, 10
[0x80000000000340]:addi t2, t2, 762
[0x80000000000344]:lui fp, 376798
[0x80000000000348]:addi fp, fp, 2941
[0x8000000000034c]:slli fp, fp, 11
[0x80000000000350]:addi fp, fp, 735
[0x80000000000354]:slli fp, fp, 11
[0x80000000000358]:addi fp, fp, 1910
[0x8000000000035c]:slli fp, fp, 10
[0x80000000000360]:addi fp, fp, 893
[0x80000000000364]:lui s1, 712687
[0x80000000000368]:addi s1, s1, 3518
[0x8000000000036c]:slli s1, s1, 11
[0x80000000000370]:addi s1, s1, 1391
[0x80000000000374]:slli s1, s1, 11
[0x80000000000378]:addi s1, s1, 1979
[0x8000000000037c]:slli s1, s1, 10
[0x80000000000380]:addi s1, s1, 446
[0x80000000000384]:lui a0, 356343
[0x80000000000388]:addi a0, a0, 1759
[0x8000000000038c]:slli a0, a0, 11
[0x80000000000390]:addi a0, a0, 695
[0x80000000000394]:slli a0, a0, 11
[0x80000000000398]:addi a0, a0, 2013
[0x8000000000039c]:slli a0, a0, 10
[0x800000000003a0]:addi a0, a0, 735
[0x800000000003a4]:lui a1, 702460
[0x800000000003a8]:addi a1, a1, 2927
[0x800000000003ac]:slli a1, a1, 11
[0x800000000003b0]:addi a1, a1, 1371
[0x800000000003b4]:slli a1, a1, 11
[0x800000000003b8]:addi a1, a1, 2030
[0x800000000003bc]:slli a1, a1, 10
[0x800000000003c0]:addi a1, a1, 879
[0x800000000003c4]:lui a2, 875518
[0x800000000003c8]:addi a2, a2, 3511
[0x800000000003cc]:slli a2, a2, 11
[0x800000000003d0]:addi a2, a2, 1709
[0x800000000003d4]:slli a2, a2, 11
[0x800000000003d8]:addi a2, a2, 2039
[0x800000000003dc]:slli a2, a2, 10
[0x800000000003e0]:addi a2, a2, 439
[0x800000000003e4]:lui a3, 962047
[0x800000000003e8]:addi a3, a3, 3803
[0x800000000003ec]:slli a3, a3, 11
[0x800000000003f0]:addi a3, a3, 1878
[0x800000000003f4]:slli a3, a3, 11
[0x800000000003f8]:addi a3, a3, 2043
[0x800000000003fc]:slli a3, a3, 10
[0x80000000000400]:addi a3, a3, 731
[0x80000000000404]:lui a4, 1005311
[0x80000000000408]:addi a4, a4, 1901
[0x8000000000040c]:slli a4, a4, 11
[0x80000000000410]:addi a4, a4, 1963
[0x80000000000414]:slli a4, a4, 11
[0x80000000000418]:addi a4, a4, 1021
[0x8000000000041c]:slli a4, a4, 10
[0x80000000000420]:addi a4, a4, 877
[0x80000000000424]:lui a5, 1026944
[0x80000000000428]:addi a5, a5, 2998
[0x8000000000042c]:slli a5, a5, 11
[0x80000000000430]:addi a5, a5, 2005
[0x80000000000434]:slli a5, a5, 11
[0x80000000000438]:addi a5, a5, 1534
[0x8000000000043c]:slli a5, a5, 10
[0x80000000000440]:addi a5, a5, 950
[0x80000000000444]:lui a6, 513472
[0x80000000000448]:addi a6, a6, 3547
[0x8000000000044c]:slli a6, a6, 11
[0x80000000000450]:addi a6, a6, 1002
[0x80000000000454]:slli a6, a6, 11
[0x80000000000458]:addi a6, a6, 1791
[0x8000000000045c]:slli a6, a6, 10
[0x80000000000460]:addi a6, a6, 475
[0x80000000000464]:lui a7, 781024
[0x80000000000468]:addi a7, a7, 3821
[0x8000000000046c]:slli a7, a7, 11
[0x80000000000470]:addi a7, a7, 1525
[0x80000000000474]:slli a7, a7, 11
[0x80000000000478]:addi a7, a7, 895
[0x8000000000047c]:slli a7, a7, 10
[0x80000000000480]:addi a7, a7, 749
[0x80000000000484]:lui s2, 914800
[0x80000000000488]:addi s2, s2, 3958
[0x8000000000048c]:slli s2, s2, 11
[0x80000000000490]:addi s2, s2, 1786
[0x80000000000494]:slli s2, s2, 11
[0x80000000000498]:addi s2, s2, 1471
[0x8000000000049c]:slli s2, s2, 10
[0x800000000004a0]:addi s2, s2, 886
[0x800000000004a4]:lui s3, 457400
[0x800000000004a8]:addi s3, s3, 4027
[0x800000000004ac]:slli s3, s3, 11
[0x800000000004b0]:addi s3, s3, 893
[0x800000000004b4]:slli s3, s3, 11
[0x800000000004b8]:addi s3, s3, 735
[0x800000000004bc]:slli s3, s3, 10
[0x800000000004c0]:addi s3, s3, 955
[0x800000000004c4]:lui s4, 752988
[0x800000000004c8]:addi s4, s4, 4061
[0x800000000004cc]:slli s4, s4, 11
[0x800000000004d0]:addi s4, s4, 1470
[0x800000000004d4]:slli s4, s4, 11
[0x800000000004d8]:addi s4, s4, 1391
[0x800000000004dc]:slli s4, s4, 10
[0x800000000004e0]:addi s4, s4, 989
[0x800000000004e4]:lui s5, 900782
[0x800000000004e8]:addi s5, s5, 4078
[0x800000000004ec]:slli s5, s5, 11
[0x800000000004f0]:addi s5, s5, 1759
[0x800000000004f4]:slli s5, s5, 11
[0x800000000004f8]:addi s5, s5, 695
[0x800000000004fc]:slli s5, s5, 10
[0x80000000000500]:addi s5, s5, 1006
[0x80000000000504]:lui s6, 450391
[0x80000000000508]:addi s6, s6, 4087
[0x8000000000050c]:slli s6, s6, 11
[0x80000000000510]:addi s6, s6, 879
[0x80000000000514]:slli s6, s6, 11
[0x80000000000518]:addi s6, s6, 1371
[0x8000000000051c]:slli s6, s6, 10
[0x80000000000520]:addi s6, s6, 1015
[0x80000000000524]:lui s7, 749483
[0x80000000000528]:addi s7, s7, 2043
[0x8000000000052c]:slli s7, s7, 11
[0x80000000000530]:addi s7, s7, 1463
[0x80000000000534]:slli s7, s7, 11
[0x80000000000538]:addi s7, s7, 1709
[0x8000000000053c]:slli s7, s7, 10
[0x80000000000540]:addi s7, s7, 1019
[0x80000000000544]:lui s8, 899030
[0x80000000000548]:addi s8, s8, 3069
[0x8000000000054c]:slli s8, s8, 11
[0x80000000000550]:addi s8, s8, 1755
[0x80000000000554]:slli s8, s8, 11
[0x80000000000558]:addi s8, s8, 1878
[0x8000000000055c]:slli s8, s8, 10
[0x80000000000560]:addi s8, s8, 1021
[0x80000000000564]:lui s9, 973803
[0x80000000000568]:addi s9, s9, 3582
[0x8000000000056c]:slli s9, s9, 11
[0x80000000000570]:addi s9, s9, 1901
[0x80000000000574]:slli s9, s9, 11
[0x80000000000578]:addi s9, s9, 1963
[0x8000000000057c]:slli s9, s9, 10
[0x80000000000580]:addi s9, s9, 510
[0x80000000000584]:lui s10, 486901
[0x80000000000588]:addi s10, s10, 1791
[0x8000000000058c]:slli s10, s10, 11
[0x80000000000590]:addi s10, s10, 950
[0x80000000000594]:slli s10, s10, 11
[0x80000000000598]:addi s10, s10, 2005
[0x8000000000059c]:slli s10, s10, 10
[0x800000000005a0]:addi s10, s10, 767
[0x800000000005a4]:lui s11, 767739
[0x800000000005a8]:addi s11, s11, 2943
[0x800000000005ac]:slli s11, s11, 11
[0x800000000005b0]:addi s11, s11, 1499
[0x800000000005b4]:slli s11, s11, 11
[0x800000000005b8]:addi s11, s11, 1002
[0x800000000005bc]:slli s11, s11, 10
[0x800000000005c0]:addi s11, s11, 895
[0x800000000005c4]:lui t3, 908157
[0x800000000005c8]:addi t3, t3, 1471
[0x800000000005cc]:slli t3, t3, 11
[0x800000000005d0]:addi t3, t3, 1773
[0x800000000005d4]:slli t3, t3, 11
[0x800000000005d8]:addi t3, t3, 1525
[0x800000000005dc]:slli t3, t3, 10
[0x800000000005e0]:addi t3, t3, 447
[0x800000000005e4]:lui t4, 978367
[0x800000000005e8]:addi t4, t4, 2783
[0x800000000005ec]:slli t4, t4, 11
[0x800000000005f0]:addi t4, t4, 1910
[0x800000000005f4]:slli t4, t4, 11
[0x800000000005f8]:addi t4, t4, 1786
[0x800000000005fc]:slli t4, t4, 10
[0x80000000000600]:addi t4, t4, 735
[0x80000000000604]:lui t5, 1013471
[0x80000000000608]:addi t5, t5, 1391
[0x8000000000060c]:slli t5, t5, 11
[0x80000000000610]:addi t5, t5, 1979
[0x80000000000614]:slli t5, t5, 11
[0x80000000000618]:addi t5, t5, 893
[0x8000000000061c]:slli t5, t5, 10
[0x80000000000620]:addi t5, t5, 367
[0x80000000000624]:lui t6, 1031024
[0x80000000000628]:addi t6, t6, 2743
[0x8000000000062c]:slli t6, t6, 11
[0x80000000000630]:addi t6, t6, 2013
[0x80000000000634]:slli t6, t6, 11
[0x80000000000638]:addi t6, t6, 1470
[0x8000000000063c]:slli t6, t6, 10
[0x80000000000640]:addi t6, t6, 695
[0x80000000000644]:addi zero, zero, 0
[0x80000000000648]:addi zero, zero, 0
[0x8000000000064c]:addi zero, zero, 0
[0x80000000000650]:addi zero, zero, 0
[0x80000000000654]:addi zero, zero, 0
[0x80000000000658]:addi zero, zero, 0
[0x8000000000065c]:addi zero, zero, 0
[0x80000000000660]:auipc a3, 7
[0x80000000000664]:addi a3, a3, 2744
[0x80000000000668]:addi zero, zero, 0
[0x8000000000066c]:addi zero, zero, 0
[0x80000000000670]:addi zero, zero, 0
[0x80000000000674]:addi zero, zero, 0
[0x80000000000678]:addi zero, zero, 0
[0x8000000000067c]:addi zero, zero, 0
[0x80000000000680]:jal zero, 16
[0x80000000000690]:lui a4, 13
[0x80000000000694]:addiw a4, a4, 3821
[0x80000000000698]:sd a4, 0(a3)
[0x8000000000069c]:lui a4, 12
[0x800000000006a0]:addiw a4, a4, 3821
[0x800000000006a4]:sd a4, 8(a3)
[0x800000000006a8]:csrrw zero, pmpcfg0, zero
[0x800000000006ac]:addi zero, zero, 0
[0x800000000006b0]:addi zero, zero, 0
[0x800000000006b4]:addi zero, zero, 0
[0x800000000006b8]:addi zero, zero, 0
[0x800000000006bc]:addi zero, zero, 0
[0x800000000006c0]:auipc t1, 0
[0x800000000006c4]:addi t1, t1, 4040
[0x800000000006c8]:addi zero, zero, 0
[0x800000000006cc]:addi zero, zero, 0
[0x800000000006d0]:addi zero, zero, 0
[0x800000000006d4]:addi zero, zero, 0
[0x800000000006d8]:addi zero, zero, 0
[0x800000000006dc]:addi zero, zero, 0
[0x800000000006e0]:auipc t2, 0
[0x800000000006e4]:addi t2, t2, 4016
[0x800000000006e8]:addi zero, zero, 0
[0x800000000006ec]:addi zero, zero, 0
[0x800000000006f0]:addi zero, zero, 0
[0x800000000006f4]:addi zero, zero, 0
[0x800000000006f8]:addi zero, zero, 0
[0x800000000006fc]:addi zero, zero, 0
[0x80000000000700]:srli t1, t1, 2
[0x80000000000704]:srli t2, t2, 2
[0x80000000000708]:csrrw zero, pmpaddr0, t1
[0x8000000000070c]:csrrw zero, pmpaddr1, t2
[0x80000000000710]:addi zero, zero, 0
[0x80000000000714]:addi zero, zero, 0
[0x80000000000718]:addi zero, zero, 0
[0x8000000000071c]:addi zero, zero, 0
[0x80000000000720]:auipc t1, 0
[0x80000000000724]:addi t1, t1, 1236
[0x80000000000728]:addi zero, zero, 0
[0x8000000000072c]:addi zero, zero, 0
[0x80000000000730]:addi zero, zero, 0
[0x80000000000734]:addi zero, zero, 0
[0x80000000000738]:addi zero, zero, 0
[0x8000000000073c]:addi zero, zero, 0
[0x80000000000740]:auipc t2, 7
[0x80000000000744]:addi t2, t2, 3032
[0x80000000000748]:addi zero, zero, 0
[0x8000000000074c]:addi zero, zero, 0
[0x80000000000750]:addi zero, zero, 0
[0x80000000000754]:addi zero, zero, 0
[0x80000000000758]:addi zero, zero, 0
[0x8000000000075c]:addi zero, zero, 0
[0x80000000000760]:srli t1, t1, 2
[0x80000000000764]:srli t2, t2, 2
[0x80000000000768]:csrrw zero, pmpaddr2, t1
[0x8000000000076c]:csrrw zero, pmpaddr3, t2
[0x80000000000770]:lui t4, 30
[0x80000000000774]:addi t4, t4, 1
[0x80000000000778]:slli t4, t4, 11
[0x8000000000077c]:csrrw zero, pmpcfg0, t4
[0x80000000000780]:addi a0, zero, 1
[0x80000000000784]:slli a0, a0, 55
[0x80000000000788]:addi a1, zero, 217
[0x8000000000078c]:srli a0, a0, 12
[0x80000000000790]:slli a0, a0, 10
[0x80000000000794]:or a0, a0, a1
[0x80000000000798]:addi zero, zero, 0
[0x8000000000079c]:addi zero, zero, 0
[0x800000000007a0]:auipc t1, 6
[0x800000000007a4]:addi t1, t1, 2144
[0x800000000007a8]:addi zero, zero, 0
[0x800000000007ac]:addi zero, zero, 0
[0x800000000007b0]:addi zero, zero, 0
[0x800000000007b4]:addi zero, zero, 0
[0x800000000007b8]:addi zero, zero, 0
[0x800000000007bc]:addi zero, zero, 0
[0x800000000007c0]:addi t0, zero, 288
[0x800000000007c4]:add t1, t1, t0
[0x800000000007c8]:sd a0, 0(t1)
[0x800000000007cc]:addi zero, zero, 0
[0x800000000007d0]:addi zero, zero, 0
[0x800000000007d4]:addi zero, zero, 0
[0x800000000007d8]:addi zero, zero, 0
[0x800000000007dc]:addi zero, zero, 0
[0x800000000007e0]:auipc a0, 0
[0x800000000007e4]:addi a0, a0, 3752
[0x800000000007e8]:addi zero, zero, 0
[0x800000000007ec]:addi zero, zero, 0
[0x800000000007f0]:addi zero, zero, 0
[0x800000000007f4]:addi zero, zero, 0
[0x800000000007f8]:addi zero, zero, 0
[0x800000000007fc]:addi zero, zero, 0
[0x80000000000800]:addi a1, zero, 215
[0x80000000000804]:srli a0, a0, 12
[0x80000000000808]:slli a0, a0, 10
[0x8000000000080c]:or a0, a0, a1
[0x80000000000810]:addi zero, zero, 0
[0x80000000000814]:addi zero, zero, 0
[0x80000000000818]:addi zero, zero, 0
[0x8000000000081c]:addi zero, zero, 0
[0x80000000000820]:auipc t1, 5
[0x80000000000824]:addi t1, t1, 2016
[0x80000000000828]:addi zero, zero, 0
[0x8000000000082c]:addi zero, zero, 0
[0x80000000000830]:addi zero, zero, 0
[0x80000000000834]:addi zero, zero, 0
[0x80000000000838]:addi zero, zero, 0
[0x8000000000083c]:addi zero, zero, 0
[0x80000000000840]:addi t0, zero, 304
[0x80000000000844]:add t1, t1, t0
[0x80000000000848]:sd a0, 0(t1)
[0x8000000000084c]:addi zero, zero, 0
[0x80000000000850]:addi zero, zero, 0
[0x80000000000854]:addi zero, zero, 0
[0x80000000000858]:addi zero, zero, 0
[0x8000000000085c]:addi zero, zero, 0
[0x80000000000860]:auipc a0, 3
[0x80000000000864]:addi a0, a0, 1952
[0x80000000000868]:addi zero, zero, 0
[0x8000000000086c]:addi zero, zero, 0
[0x80000000000870]:addi zero, zero, 0
[0x80000000000874]:addi zero, zero, 0
[0x80000000000878]:addi zero, zero, 0
[0x8000000000087c]:addi zero, zero, 0
[0x80000000000880]:addi a1, zero, 1
[0x80000000000884]:srli a0, a0, 12
[0x80000000000888]:slli a0, a0, 10
[0x8000000000088c]:or a0, a0, a1
[0x80000000000890]:addi zero, zero, 0
[0x80000000000894]:addi zero, zero, 0
[0x80000000000898]:addi zero, zero, 0
[0x8000000000089c]:addi zero, zero, 0
[0x800000000008a0]:auipc t1, 5
[0x800000000008a4]:addi t1, t1, 1888
[0x800000000008a8]:addi zero, zero, 0
[0x800000000008ac]:addi zero, zero, 0
[0x800000000008b0]:addi zero, zero, 0
[0x800000000008b4]:addi zero, zero, 0
[0x800000000008b8]:addi zero, zero, 0
[0x800000000008bc]:addi zero, zero, 0
[0x800000000008c0]:addi t0, zero, 320
[0x800000000008c4]:add t1, t1, t0
[0x800000000008c8]:sd a0, 0(t1)
[0x800000000008cc]:addi zero, zero, 0
[0x800000000008d0]:addi zero, zero, 0
[0x800000000008d4]:addi zero, zero, 0
[0x800000000008d8]:addi zero, zero, 0
[0x800000000008dc]:addi zero, zero, 0
[0x800000000008e0]:auipc a0, 4
[0x800000000008e4]:addi a0, a0, 1824
[0x800000000008e8]:addi zero, zero, 0
[0x800000000008ec]:addi zero, zero, 0
[0x800000000008f0]:addi zero, zero, 0
[0x800000000008f4]:addi zero, zero, 0
[0x800000000008f8]:addi zero, zero, 0
[0x800000000008fc]:addi zero, zero, 0
[0x80000000000900]:addi a1, zero, 1
[0x80000000000904]:srli a0, a0, 12
[0x80000000000908]:slli a0, a0, 10
[0x8000000000090c]:or a0, a0, a1
[0x80000000000910]:addi zero, zero, 0
[0x80000000000914]:addi zero, zero, 0
[0x80000000000918]:addi zero, zero, 0
[0x8000000000091c]:addi zero, zero, 0
[0x80000000000920]:auipc t1, 3
[0x80000000000924]:addi t1, t1, 1760
[0x80000000000928]:addi zero, zero, 0
[0x8000000000092c]:addi zero, zero, 0
[0x80000000000930]:addi zero, zero, 0
[0x80000000000934]:addi zero, zero, 0
[0x80000000000938]:addi zero, zero, 0
[0x8000000000093c]:addi zero, zero, 0
[0x80000000000940]:addi t0, zero, 0
[0x80000000000944]:add t1, t1, t0
[0x80000000000948]:sd a0, 0(t1)
[0x8000000000094c]:auipc a0, 6
[0x80000000000950]:addi a0, a0, 1988
[0x80000000000954]:addi a1, zero, 215
[0x80000000000958]:srli a0, a0, 12
[0x8000000000095c]:slli a0, a0, 10
[0x80000000000960]:or a0, a0, a1
[0x80000000000964]:addi zero, zero, 0
[0x80000000000968]:addi zero, zero, 0
[0x8000000000096c]:addi zero, zero, 0
[0x80000000000970]:addi zero, zero, 0
[0x80000000000974]:addi zero, zero, 0
[0x80000000000978]:addi zero, zero, 0
[0x8000000000097c]:addi zero, zero, 0
[0x80000000000980]:auipc t1, 4
[0x80000000000984]:addi t1, t1, 1664
[0x80000000000988]:addi zero, zero, 0
[0x8000000000098c]:addi zero, zero, 0
[0x80000000000990]:addi zero, zero, 0
[0x80000000000994]:addi zero, zero, 0
[0x80000000000998]:addi zero, zero, 0
[0x8000000000099c]:addi zero, zero, 0
[0x800000000009a0]:addi t0, zero, 0
[0x800000000009a4]:add t1, t1, t0
[0x800000000009a8]:sd a0, 0(t1)
[0x800000000009ac]:lui t0, 0
[0x800000000009b0]:addi t0, t0, 10
[0x800000000009b4]:slli t0, t0, 11
[0x800000000009b8]:addi t0, t0, 0
[0x800000000009bc]:slli t0, t0, 11
[0x800000000009c0]:addi t0, t0, 0
[0x800000000009c4]:slli t0, t0, 10
[0x800000000009c8]:addi t0, t0, 280
[0x800000000009cc]:addi zero, zero, 0
[0x800000000009d0]:addi zero, zero, 0
[0x800000000009d4]:addi zero, zero, 0
[0x800000000009d8]:addi zero, zero, 0
[0x800000000009dc]:addi zero, zero, 0
[0x800000000009e0]:auipc t1, 6
[0x800000000009e4]:addi t1, t1, 1840
[0x800000000009e8]:addi zero, zero, 0
[0x800000000009ec]:addi zero, zero, 0
[0x800000000009f0]:addi zero, zero, 0
[0x800000000009f4]:addi zero, zero, 0
[0x800000000009f8]:addi zero, zero, 0
[0x800000000009fc]:addi zero, zero, 0
[0x80000000000a00]:sub t0, t0, t1
[0x80000000000a04]:add s11, a3, t0
[0x80000000000a08]:addi zero, zero, 0
[0x80000000000a0c]:addi zero, zero, 0
[0x80000000000a10]:addi zero, zero, 0
[0x80000000000a14]:addi zero, zero, 0
[0x80000000000a18]:addi zero, zero, 0
[0x80000000000a1c]:addi zero, zero, 0
[0x80000000000a20]:auipc t6, 5
[0x80000000000a24]:addi t6, t6, 1504
[0x80000000000a28]:addi zero, zero, 0
[0x80000000000a2c]:addi zero, zero, 0
[0x80000000000a30]:addi zero, zero, 0
[0x80000000000a34]:addi zero, zero, 0
[0x80000000000a38]:addi zero, zero, 0
[0x80000000000a3c]:addi zero, zero, 0
[0x80000000000a40]:addi t5, zero, 4095
[0x80000000000a44]:slli t5, t5, 63
[0x80000000000a48]:srli t6, t6, 12
[0x80000000000a4c]:or t6, t6, t5
[0x80000000000a50]:csrrw zero, satp, t6
[0x80000000000a54]:addi t0, zero, 9
[0x80000000000a58]:slli t0, t0, 32
[0x80000000000a5c]:addi t1, zero, 1
[0x80000000000a60]:slli t1, t1, 55
[0x80000000000a64]:sub t0, t0, t1
[0x80000000000a68]:csrrs sp, mscratch, zero
[0x80000000000a6c]:add t1, sp, t0
[0x80000000000a70]:csrrw zero, sscratch, t1
[0x80000000000a74]:ld t1, 472(sp)
[0x80000000000a78]:add t2, t1, t0
[0x80000000000a7c]:sd t2, 1136(sp)
[0x80000000000a80]:sd t2, 1800(sp)
[0x80000000000a84]:lui t0, 0
[0x80000000000a88]:addi t0, t0, 9
[0x80000000000a8c]:slli t0, t0, 11
[0x80000000000a90]:addi t0, t0, 1024
[0x80000000000a94]:slli t0, t0, 11
[0x80000000000a98]:addi t0, t0, 1
[0x80000000000a9c]:slli t0, t0, 10
[0x80000000000aa0]:addi t0, t0, 648
[0x80000000000aa4]:addi zero, zero, 0
[0x80000000000aa8]:addi zero, zero, 0
[0x80000000000aac]:addi zero, zero, 0
[0x80000000000ab0]:addi zero, zero, 0
[0x80000000000ab4]:addi zero, zero, 0
[0x80000000000ab8]:addi zero, zero, 0
[0x80000000000abc]:addi zero, zero, 0
[0x80000000000ac0]:auipc t1, 0
[0x80000000000ac4]:addi t1, t1, 3016
[0x80000000000ac8]:addi zero, zero, 0
[0x80000000000acc]:addi zero, zero, 0
[0x80000000000ad0]:addi zero, zero, 0
[0x80000000000ad4]:addi zero, zero, 0
[0x80000000000ad8]:addi zero, zero, 0
[0x80000000000adc]:addi zero, zero, 0
[0x80000000000ae0]:sub t0, t0, t1
[0x80000000000ae4]:ld t1, 488(sp)
[0x80000000000ae8]:add t2, t1, t0
[0x80000000000aec]:sd t2, 1152(sp)
[0x80000000000af0]:sd t2, 1816(sp)
[0x80000000000af4]:lui t0, 0
[0x80000000000af8]:addi t0, t0, 10
[0x80000000000afc]:slli t0, t0, 11
[0x80000000000b00]:addi t0, t0, 0
[0x80000000000b04]:slli t0, t0, 11
[0x80000000000b08]:addi t0, t0, 0
[0x80000000000b0c]:slli t0, t0, 10
[0x80000000000b10]:addi t0, t0, 280
[0x80000000000b14]:addi zero, zero, 0
[0x80000000000b18]:addi zero, zero, 0
[0x80000000000b1c]:addi zero, zero, 0
[0x80000000000b20]:auipc t1, 6
[0x80000000000b24]:addi t1, t1, 1528
[0x80000000000b28]:addi zero, zero, 0
[0x80000000000b2c]:addi zero, zero, 0
[0x80000000000b30]:addi zero, zero, 0
[0x80000000000b34]:addi zero, zero, 0
[0x80000000000b38]:addi zero, zero, 0
[0x80000000000b3c]:addi zero, zero, 0
[0x80000000000b40]:sub t0, t0, t1
[0x80000000000b44]:ld t1, 504(sp)
[0x80000000000b48]:add t2, t1, t0
[0x80000000000b4c]:sd t2, 1168(sp)
[0x80000000000b50]:sd t2, 1832(sp)
[0x80000000000b54]:lui t0, 0
[0x80000000000b58]:addi t0, t0, 9
[0x80000000000b5c]:slli t0, t0, 11
[0x80000000000b60]:addi t0, t0, 1024
[0x80000000000b64]:slli t0, t0, 11
[0x80000000000b68]:addi t0, t0, 1
[0x80000000000b6c]:slli t0, t0, 10
[0x80000000000b70]:addi t0, t0, 648
[0x80000000000b74]:addi zero, zero, 0
[0x80000000000b78]:addi zero, zero, 0
[0x80000000000b7c]:addi zero, zero, 0
[0x80000000000b80]:auipc t1, 0
[0x80000000000b84]:addi t1, t1, 2824
[0x80000000000b88]:addi zero, zero, 0
[0x80000000000b8c]:addi zero, zero, 0
[0x80000000000b90]:addi zero, zero, 0
[0x80000000000b94]:addi zero, zero, 0
[0x80000000000b98]:addi zero, zero, 0
[0x80000000000b9c]:addi zero, zero, 0
[0x80000000000ba0]:sub t0, t0, t1
[0x80000000000ba4]:ld t1, 520(sp)
[0x80000000000ba8]:add t2, t1, t0
[0x80000000000bac]:sd t2, 1184(sp)
[0x80000000000bb0]:sd t2, 1848(sp)
[0x80000000000bb4]:sfence.vma zero, zero
[0x80000000000bb8]:addi s1, zero, 4095
[0x80000000000bbc]:srli s1, s1, 62
[0x80000000000bc0]:slli s1, s1, 11
[0x80000000000bc4]:csrrc zero, mstatus, s1
[0x80000000000bc8]:csrrs sp, mscratch, zero
[0x80000000000bcc]:ld t1, 1800(sp)
[0x80000000000bd0]:ld s1, 472(sp)
[0x80000000000bd4]:sub t1, t1, s1
[0x80000000000bd8]:addi t1, t1, 16
[0x80000000000bdc]:auipc s1, 0
[0x80000000000be0]:add s1, s1, t1
[0x80000000000be4]:csrrw s1, mepc, s1
[0x80000000000be8]:mret
[0x80000000000d80]:jal zero, 256
[0x80000000000e80]:csrrw sp, mscratch, sp

[0x80000000000ff8]:sd a0, 8(t1)
[0x80000000000ffc]:blt a0, zero, 324
[0x80000000001000]:addi s1, sp, 0
[0x80000000001004]:csrrs a1, mstatus, zero

[0x100c]:ld t0, 24(t0)
[0x1010]:jalr zero, t0, 0
[0x80000000000000]:auipc t1, 3
[0x80000000000004]:addi t1, t1, 0
[0x80000000000008]:addi zero, zero, 0
[0x8000000000000c]:addi zero, zero, 0
[0x80000000000010]:addi zero, zero, 0
[0x80000000000014]:addi zero, zero, 0
[0x80000000000018]:addi zero, zero, 0
[0x8000000000001c]:addi zero, zero, 0
[0x80000000000020]:csrrw fp, mscratch, t1
[0x80000000000024]:sd fp, 592(t1)
[0x80000000000028]:addi t2, zero, 0
[0x8000000000002c]:csrrw t2, medeleg, t2
[0x80000000000030]:sd t2, 568(t1)
[0x80000000000034]:addi zero, zero, 0
[0x80000000000038]:addi zero, zero, 0
[0x8000000000003c]:addi zero, zero, 0
[0x80000000000040]:auipc s1, 1
[0x80000000000044]:addi s1, s1, 3392
[0x80000000000048]:addi zero, zero, 0
[0x8000000000004c]:addi zero, zero, 0
[0x80000000000050]:addi zero, zero, 0
[0x80000000000054]:addi zero, zero, 0
[0x80000000000058]:addi zero, zero, 0
[0x8000000000005c]:addi zero, zero, 0
[0x80000000000060]:addi fp, s1, 468
[0x80000000000064]:sd fp, 560(t1)
[0x80000000000068]:csrrs fp, mtvec, zero
[0x8000000000006c]:sd fp, 584(t1)
[0x80000000000070]:andi t2, fp, 3
[0x80000000000074]:or t2, s1, t2
[0x80000000000078]:sd t2, 576(t1)
[0x8000000000007c]:csrrw zero, mtvec, t2
[0x80000000000080]:csrrs a0, mtvec, zero
[0x80000000000084]:beq a0, t2, 128
[0x80000000000104]:addi zero, zero, 0
[0x80000000000108]:addi zero, zero, 0
[0x8000000000010c]:addi zero, zero, 0
[0x80000000000110]:addi zero, zero, 0
[0x80000000000114]:addi zero, zero, 0
[0x80000000000118]:addi zero, zero, 0
[0x8000000000011c]:addi zero, zero, 0
[0x80000000000120]:auipc t1, 3
[0x80000000000124]:addi t1, t1, 376
[0x80000000000128]:addi zero, zero, 0
[0x8000000000012c]:addi zero, zero, 0
[0x80000000000130]:addi zero, zero, 0
[0x80000000000134]:addi zero, zero, 0
[0x80000000000138]:addi zero, zero, 0
[0x8000000000013c]:addi zero, zero, 0
[0x80000000000140]:csrrw fp, sscratch, t1
[0x80000000000144]:sd fp, 592(t1)
[0x80000000000148]:addi t2, zero, 0
[0x8000000000014c]:sd t2, 568(t1)
[0x80000000000150]:addi zero, zero, 0
[0x80000000000154]:addi zero, zero, 0
[0x80000000000158]:addi zero, zero, 0
[0x8000000000015c]:addi zero, zero, 0
[0x80000000000160]:auipc s1, 6
[0x80000000000164]:addi s1, s1, 3744
[0x80000000000168]:addi zero, zero, 0
[0x8000000000016c]:addi zero, zero, 0
[0x80000000000170]:addi zero, zero, 0
[0x80000000000174]:addi zero, zero, 0
[0x80000000000178]:addi zero, zero, 0
[0x8000000000017c]:addi zero, zero, 0
[0x80000000000180]:csrrw s1, satp, s1
[0x80000000000184]:sd s1, 544(t1)
[0x80000000000188]:addi zero, zero, 0
[0x8000000000018c]:addi zero, zero, 0
[0x80000000000190]:addi zero, zero, 0
[0x80000000000194]:addi zero, zero, 0
[0x80000000000198]:addi zero, zero, 0
[0x8000000000019c]:addi zero, zero, 0
[0x800000000001a0]:auipc s1, 1
[0x800000000001a4]:addi s1, s1, 1184
[0x800000000001a8]:addi zero, zero, 0
[0x800000000001ac]:addi zero, zero, 0
[0x800000000001b0]:addi zero, zero, 0
[0x800000000001b4]:addi zero, zero, 0
[0x800000000001b8]:addi zero, zero, 0
[0x800000000001bc]:addi zero, zero, 0
[0x800000000001c0]:addi fp, s1, 468
[0x800000000001c4]:sd fp, 560(t1)
[0x800000000001c8]:csrrs fp, stvec, zero
[0x800000000001cc]:sd fp, 584(t1)
[0x800000000001d0]:andi t2, fp, 3
[0x800000000001d4]:or t2, s1, t2
[0x800000000001d8]:sd t2, 576(t1)
[0x800000000001dc]:csrrw zero, stvec, t2
[0x800000000001e0]:csrrs a0, stvec, zero
[0x800000000001e4]:beq a0, t2, 128
[0x80000000000264]:lui ra, 1044188
[0x80000000000268]:addi ra, ra, 3757
[0x8000000000026c]:slli ra, ra, 11
[0x80000000000270]:addi ra, ra, 2039
[0x80000000000274]:slli ra, ra, 11
[0x80000000000278]:addi ra, ra, 879
[0x8000000000027c]:slli ra, ra, 10
[0x80000000000280]:addi ra, ra, 685
[0x80000000000284]:lui sp, 1046382
[0x80000000000288]:addi sp, sp, 3926
[0x8000000000028c]:slli sp, sp, 11
[0x80000000000290]:addi sp, sp, 2043
[0x80000000000294]:slli sp, sp, 11
[0x80000000000298]:addi sp, sp, 1463
[0x8000000000029c]:slli sp, sp, 10
[0x800000000002a0]:addi sp, sp, 854
[0x800000000002a4]:lui gp, 523191
[0x800000000002a8]:addi gp, gp, 4011
[0x800000000002ac]:slli gp, gp, 11
[0x800000000002b0]:addi gp, gp, 1021
[0x800000000002b4]:slli gp, gp, 11
[0x800000000002b8]:addi gp, gp, 1755
[0x800000000002bc]:slli gp, gp, 10
[0x800000000002c0]:addi gp, gp, 939
[0x800000000002c4]:lui tp, 785883
[0x800000000002c8]:addi tp, tp, 2005
[0x800000000002cc]:slli tp, tp, 11
[0x800000000002d0]:addi tp, tp, 1534
[0x800000000002d4]:slli tp, tp, 11
[0x800000000002d8]:addi tp, tp, 1901
[0x800000000002dc]:slli tp, tp, 10
[0x800000000002e0]:addi tp, tp, 981
[0x800000000002e4]:lui t0, 917230
[0x800000000002e8]:addi t0, t0, 3050
[0x800000000002ec]:slli t0, t0, 11
[0x800000000002f0]:addi t0, t0, 1791
[0x800000000002f4]:slli t0, t0, 11
[0x800000000002f8]:addi t0, t0, 950
[0x800000000002fc]:slli t0, t0, 10
[0x80000000000300]:addi t0, t0, 1002
[0x80000000000304]:lui t1, 458615
[0x80000000000308]:addi t1, t1, 3573
[0x8000000000030c]:slli t1, t1, 11
[0x80000000000310]:addi t1, t1, 895
[0x80000000000314]:slli t1, t1, 11
[0x80000000000318]:addi t1, t1, 1499
[0x8000000000031c]:slli t1, t1, 10
[0x80000000000320]:addi t1, t1, 501
[0x80000000000324]:lui t2, 753595
[0x80000000000328]:addi t2, t2, 1786
[0x8000000000032c]:slli t2, t2, 11
[0x80000000000330]:addi t2, t2, 1471
[0x80000000000334]:slli t2, t2, 11
[0x80000000000338]:addi t2, t2, 1773
[0x8000000000033c]:slli t2, t2, 10
[0x80000000000340]:addi t2, t2, 762
[0x80000000000344]:lui fp, 376798
[0x80000000000348]:addi fp, fp, 2941
[0x8000000000034c]:slli fp, fp, 11
[0x80000000000350]:addi fp, fp, 735
[0x80000000000354]:slli fp, fp, 11
[0x80000000000358]:addi fp, fp, 1910
[0x8000000000035c]:slli fp, fp, 10
[0x80000000000360]:addi fp, fp, 893
[0x80000000000364]:lui s1, 712687
[0x80000000000368]:addi s1, s1, 3518
[0x8000000000036c]:slli s1, s1, 11
[0x80000000000370]:addi s1, s1, 1391
[0x80000000000374]:slli s1, s1, 11
[0x80000000000378]:addi s1, s1, 1979
[0x8000000000037c]:slli s1, s1, 10
[0x80000000000380]:addi s1, s1, 446
[0x80000000000384]:lui a0, 356343
[0x80000000000388]:addi a0, a0, 1759
[0x8000000000038c]:slli a0, a0, 11
[0x80000000000390]:addi a0, a0, 695
[0x80000000000394]:slli a0, a0, 11
[0x80000000000398]:addi a0, a0, 2013
[0x8000000000039c]:slli a0, a0, 10
[0x800000000003a0]:addi a0, a0, 735
[0x800000000003a4]:lui a1, 702460
[0x800000000003a8]:addi a1, a1, 2927
[0x800000000003ac]:slli a1, a1, 11
[0x800000000003b0]:addi a1, a1, 1371
[0x800000000003b4]:slli a1, a1, 11
[0x800000000003b8]:addi a1, a1, 2030
[0x800000000003bc]:slli a1, a1, 10
[0x800000000003c0]:addi a1, a1, 879
[0x800000000003c4]:lui a2, 875518
[0x800000000003c8]:addi a2, a2, 3511
[0x800000000003cc]:slli a2, a2, 11
[0x800000000003d0]:addi a2, a2, 1709
[0x800000000003d4]:slli a2, a2, 11
[0x800000000003d8]:addi a2, a2, 2039
[0x800000000003dc]:slli a2, a2, 10
[0x800000000003e0]:addi a2, a2, 439
[0x800000000003e4]:lui a3, 962047
[0x800000000003e8]:addi a3, a3, 3803
[0x800000000003ec]:slli a3, a3, 11
[0x800000000003f0]:addi a3, a3, 1878
[0x800000000003f4]:slli a3, a3, 11
[0x800000000003f8]:addi a3, a3, 2043
[0x800000000003fc]:slli a3, a3, 10
[0x80000000000400]:addi a3, a3, 731
[0x80000000000404]:lui a4, 1005311
[0x80000000000408]:addi a4, a4, 1901
[0x8000000000040c]:slli a4, a4, 11
[0x80000000000410]:addi a4, a4, 1963
[0x80000000000414]:slli a4, a4, 11
[0x80000000000418]:addi a4, a4, 1021
[0x8000000000041c]:slli a4, a4, 10
[0x80000000000420]:addi a4, a4, 877
[0x80000000000424]:lui a5, 1026944
[0x80000000000428]:addi a5, a5, 2998
[0x8000000000042c]:slli a5, a5, 11
[0x80000000000430]:addi a5, a5, 2005
[0x80000000000434]:slli a5, a5, 11
[0x80000000000438]:addi a5, a5, 1534
[0x8000000000043c]:slli a5, a5, 10
[0x80000000000440]:addi a5, a5, 950
[0x80000000000444]:lui a6, 513472
[0x80000000000448]:addi a6, a6, 3547
[0x8000000000044c]:slli a6, a6, 11
[0x80000000000450]:addi a6, a6, 1002
[0x80000000000454]:slli a6, a6, 11
[0x80000000000458]:addi a6, a6, 1791
[0x8000000000045c]:slli a6, a6, 10
[0x80000000000460]:addi a6, a6, 475
[0x80000000000464]:lui a7, 781024
[0x80000000000468]:addi a7, a7, 3821
[0x8000000000046c]:slli a7, a7, 11
[0x80000000000470]:addi a7, a7, 1525
[0x80000000000474]:slli a7, a7, 11
[0x80000000000478]:addi a7, a7, 895
[0x8000000000047c]:slli a7, a7, 10
[0x80000000000480]:addi a7, a7, 749
[0x80000000000484]:lui s2, 914800
[0x80000000000488]:addi s2, s2, 3958
[0x8000000000048c]:slli s2, s2, 11
[0x80000000000490]:addi s2, s2, 1786
[0x80000000000494]:slli s2, s2, 11
[0x80000000000498]:addi s2, s2, 1471
[0x8000000000049c]:slli s2, s2, 10
[0x800000000004a0]:addi s2, s2, 886
[0x800000000004a4]:lui s3, 457400
[0x800000000004a8]:addi s3, s3, 4027
[0x800000000004ac]:slli s3, s3, 11
[0x800000000004b0]:addi s3, s3, 893
[0x800000000004b4]:slli s3, s3, 11
[0x800000000004b8]:addi s3, s3, 735
[0x800000000004bc]:slli s3, s3, 10
[0x800000000004c0]:addi s3, s3, 955
[0x800000000004c4]:lui s4, 752988
[0x800000000004c8]:addi s4, s4, 4061
[0x800000000004cc]:slli s4, s4, 11
[0x800000000004d0]:addi s4, s4, 1470
[0x800000000004d4]:slli s4, s4, 11
[0x800000000004d8]:addi s4, s4, 1391
[0x800000000004dc]:slli s4, s4, 10
[0x800000000004e0]:addi s4, s4, 989
[0x800000000004e4]:lui s5, 900782
[0x800000000004e8]:addi s5, s5, 4078
[0x800000000004ec]:slli s5, s5, 11
[0x800000000004f0]:addi s5, s5, 1759
[0x800000000004f4]:slli s5, s5, 11
[0x800000000004f8]:addi s5, s5, 695
[0x800000000004fc]:slli s5, s5, 10
[0x80000000000500]:addi s5, s5, 1006
[0x80000000000504]:lui s6, 450391
[0x80000000000508]:addi s6, s6, 4087
[0x8000000000050c]:slli s6, s6, 11
[0x80000000000510]:addi s6, s6, 879
[0x80000000000514]:slli s6, s6, 11
[0x80000000000518]:addi s6, s6, 1371
[0x8000000000051c]:slli s6, s6, 10
[0x80000000000520]:addi s6, s6, 1015
[0x80000000000524]:lui s7, 749483
[0x80000000000528]:addi s7, s7, 2043
[0x8000000000052c]:slli s7, s7, 11
[0x80000000000530]:addi s7, s7, 1463
[0x80000000000534]:slli s7, s7, 11
[0x80000000000538]:addi s7, s7, 1709
[0x8000000000053c]:slli s7, s7, 10
[0x80000000000540]:addi s7, s7, 1019
[0x80000000000544]:lui s8, 899030
[0x80000000000548]:addi s8, s8, 3069
[0x8000000000054c]:slli s8, s8, 11
[0x80000000000550]:addi s8, s8, 1755
[0x80000000000554]:slli s8, s8, 11
[0x80000000000558]:addi s8, s8, 1878
[0x8000000000055c]:slli s8, s8, 10
[0x80000000000560]:addi s8, s8, 1021
[0x80000000000564]:lui s9, 973803
[0x80000000000568]:addi s9, s9, 3582
[0x8000000000056c]:slli s9, s9, 11
[0x80000000000570]:addi s9, s9, 1901
[0x80000000000574]:slli s9, s9, 11
[0x80000000000578]:addi s9, s9, 1963
[0x8000000000057c]:slli s9, s9, 10
[0x80000000000580]:addi s9, s9, 510
[0x80000000000584]:lui s10, 486901
[0x80000000000588]:addi s10, s10, 1791
[0x8000000000058c]:slli s10, s10, 11
[0x80000000000590]:addi s10, s10, 950
[0x80000000000594]:slli s10, s10, 11
[0x80000000000598]:addi s10, s10, 2005
[0x8000000000059c]:slli s10, s10, 10
[0x800000000005a0]:addi s10, s10, 767
[0x800000000005a4]:lui s11, 767739
[0x800000000005a8]:addi s11, s11, 2943
[0x800000000005ac]:slli s11, s11, 11
[0x800000000005b0]:addi s11, s11, 1499
[0x800000000005b4]:slli s11, s11, 11
[0x800000000005b8]:addi s11, s11, 1002
[0x800000000005bc]:slli s11, s11, 10
[0x800000000005c0]:addi s11, s11, 895
[0x800000000005c4]:lui t3, 908157
[0x800000000005c8]:addi t3, t3, 1471
[0x800000000005cc]:slli t3, t3, 11
[0x800000000005d0]:addi t3, t3, 1773
[0x800000000005d4]:slli t3, t3, 11
[0x800000000005d8]:addi t3, t3, 1525
[0x800000000005dc]:slli t3, t3, 10
[0x800000000005e0]:addi t3, t3, 447
[0x800000000005e4]:lui t4, 978367
[0x800000000005e8]:addi t4, t4, 2783
[0x800000000005ec]:slli t4, t4, 11
[0x800000000005f0]:addi t4, t4, 1910
[0x800000000005f4]:slli t4, t4, 11
[0x800000000005f8]:addi t4, t4, 1786
[0x800000000005fc]:slli t4, t4, 10
[0x80000000000600]:addi t4, t4, 735
[0x80000000000604]:lui t5, 1013471
[0x80000000000608]:addi t5, t5, 1391
[0x8000000000060c]:slli t5, t5, 11
[0x80000000000610]:addi t5, t5, 1979
[0x80000000000614]:slli t5, t5, 11
[0x80000000000618]:addi t5, t5, 893
[0x8000000000061c]:slli t5, t5, 10
[0x80000000000620]:addi t5, t5, 367
[0x80000000000624]:lui t6, 1031024
[0x80000000000628]:addi t6, t6, 2743
[0x8000000000062c]:slli t6, t6, 11
[0x80000000000630]:addi t6, t6, 2013
[0x80000000000634]:slli t6, t6, 11
[0x80000000000638]:addi t6, t6, 1470
[0x8000000000063c]:slli t6, t6, 10
[0x80000000000640]:addi t6, t6, 695
[0x80000000000644]:addi zero, zero, 0
[0x80000000000648]:addi zero, zero, 0
[0x8000000000064c]:addi zero, zero, 0
[0x80000000000650]:addi zero, zero, 0
[0x80000000000654]:addi zero, zero, 0
[0x80000000000658]:addi zero, zero, 0
[0x8000000000065c]:addi zero, zero, 0
[0x80000000000660]:auipc a3, 7
[0x80000000000664]:addi a3, a3, 2744
[0x80000000000668]:addi zero, zero, 0
[0x8000000000066c]:addi zero, zero, 0
[0x80000000000670]:addi zero, zero, 0
[0x80000000000674]:addi zero, zero, 0
[0x80000000000678]:addi zero, zero, 0
[0x8000000000067c]:addi zero, zero, 0
[0x80000000000680]:jal zero, 16
[0x80000000000690]:lui a4, 13
[0x80000000000694]:addiw a4, a4, 3821
[0x80000000000698]:sd a4, 0(a3)
[0x8000000000069c]:lui a4, 12
[0x800000000006a0]:addiw a4, a4, 3821
[0x800000000006a4]:sd a4, 8(a3)
[0x800000000006a8]:csrrw zero, pmpcfg0, zero
[0x800000000006ac]:addi zero, zero, 0
[0x800000000006b0]:addi zero, zero, 0
[0x800000000006b4]:addi zero, zero, 0
[0x800000000006b8]:addi zero, zero, 0
[0x800000000006bc]:addi zero, zero, 0
[0x800000000006c0]:auipc t1, 0
[0x800000000006c4]:addi t1, t1, 4040
[0x800000000006c8]:addi zero, zero, 0
[0x800000000006cc]:addi zero, zero, 0
[0x800000000006d0]:addi zero, zero, 0
[0x800000000006d4]:addi zero, zero, 0
[0x800000000006d8]:addi zero, zero, 0
[0x800000000006dc]:addi zero, zero, 0
[0x800000000006e0]:auipc t2, 0
[0x800000000006e4]:addi t2, t2, 4016
[0x800000000006e8]:addi zero, zero, 0
[0x800000000006ec]:addi zero, zero, 0
[0x800000000006f0]:addi zero, zero, 0
[0x800000000006f4]:addi zero, zero, 0
[0x800000000006f8]:addi zero, zero, 0
[0x800000000006fc]:addi zero, zero, 0
[0x80000000000700]:srli t1, t1, 2
[0x80000000000704]:srli t2, t2, 2
[0x80000000000708]:csrrw zero, pmpaddr0, t1
[0x8000000000070c]:csrrw zero, pmpaddr1, t2
[0x80000000000710]:addi zero, zero, 0
[0x80000000000714]:addi zero, zero, 0
[0x80000000000718]:addi zero, zero, 0
[0x8000000000071c]:addi zero, zero, 0
[0x80000000000720]:auipc t1, 0
[0x80000000000724]:addi t1, t1, 1236
[0x80000000000728]:addi zero, zero, 0
[0x8000000000072c]:addi zero, zero, 0
[0x80000000000730]:addi zero, zero, 0
[0x80000000000734]:addi zero, zero, 0
[0x80000000000738]:addi zero, zero, 0
[0x8000000000073c]:addi zero, zero, 0
[0x80000000000740]:auipc t2, 7
[0x80000000000744]:addi t2, t2, 3032
[0x80000000000748]:addi zero, zero, 0
[0x8000000000074c]:addi zero, zero, 0
[0x80000000000750]:addi zero, zero, 0
[0x80000000000754]:addi zero, zero, 0
[0x80000000000758]:addi zero, zero, 0
[0x8000000000075c]:addi zero, zero, 0
[0x80000000000760]:srli t1, t1, 2
[0x80000000000764]:srli t2, t2, 2
[0x80000000000768]:csrrw zero, pmpaddr2, t1
[0x8000000000076c]:csrrw zero, pmpaddr3, t2
[0x80000000000770]:lui t4, 30
[0x80000000000774]:addi t4, t4, 1
[0x80000000000778]:slli t4, t4, 11
[0x8000000000077c]:csrrw zero, pmpcfg0, t4
[0x80000000000780]:addi a0, zero, 1
[0x80000000000784]:slli a0, a0, 55
[0x80000000000788]:addi a1, zero, 217
[0x8000000000078c]:srli a0, a0, 12
[0x80000000000790]:slli a0, a0, 10
[0x80000000000794]:or a0, a0, a1
[0x80000000000798]:addi zero, zero, 0
[0x8000000000079c]:addi zero, zero, 0
[0x800000000007a0]:auipc t1, 6
[0x800000000007a4]:addi t1, t1, 2144
[0x800000000007a8]:addi zero, zero, 0
[0x800000000007ac]:addi zero, zero, 0
[0x800000000007b0]:addi zero, zero, 0
[0x800000000007b4]:addi zero, zero, 0
[0x800000000007b8]:addi zero, zero, 0
[0x800000000007bc]:addi zero, zero, 0
[0x800000000007c0]:addi t0, zero, 288
[0x800000000007c4]:add t1, t1, t0
[0x800000000007c8]:sd a0, 0(t1)
[0x800000000007cc]:addi zero, zero, 0
[0x800000000007d0]:addi zero, zero, 0
[0x800000000007d4]:addi zero, zero, 0
[0x800000000007d8]:addi zero, zero, 0
[0x800000000007dc]:addi zero, zero, 0
[0x800000000007e0]:auipc a0, 0
[0x800000000007e4]:addi a0, a0, 3752
[0x800000000007e8]:addi zero, zero, 0
[0x800000000007ec]:addi zero, zero, 0
[0x800000000007f0]:addi zero, zero, 0
[0x800000000007f4]:addi zero, zero, 0
[0x800000000007f8]:addi zero, zero, 0
[0x800000000007fc]:addi zero, zero, 0
[0x80000000000800]:addi a1, zero, 215
[0x80000000000804]:srli a0, a0, 12
[0x80000000000808]:slli a0, a0, 10
[0x8000000000080c]:or a0, a0, a1
[0x80000000000810]:addi zero, zero, 0
[0x80000000000814]:addi zero, zero, 0
[0x80000000000818]:addi zero, zero, 0
[0x8000000000081c]:addi zero, zero, 0
[0x80000000000820]:auipc t1, 5
[0x80000000000824]:addi t1, t1, 2016
[0x80000000000828]:addi zero, zero, 0
[0x8000000000082c]:addi zero, zero, 0
[0x80000000000830]:addi zero, zero, 0
[0x80000000000834]:addi zero, zero, 0
[0x80000000000838]:addi zero, zero, 0
[0x8000000000083c]:addi zero, zero, 0
[0x80000000000840]:addi t0, zero, 304
[0x80000000000844]:add t1, t1, t0
[0x80000000000848]:sd a0, 0(t1)
[0x8000000000084c]:addi zero, zero, 0
[0x80000000000850]:addi zero, zero, 0
[0x80000000000854]:addi zero, zero, 0
[0x80000000000858]:addi zero, zero, 0
[0x8000000000085c]:addi zero, zero, 0
[0x80000000000860]:auipc a0, 3
[0x80000000000864]:addi a0, a0, 1952
[0x80000000000868]:addi zero, zero, 0
[0x8000000000086c]:addi zero, zero, 0
[0x80000000000870]:addi zero, zero, 0
[0x80000000000874]:addi zero, zero, 0
[0x80000000000878]:addi zero, zero, 0
[0x8000000000087c]:addi zero, zero, 0
[0x80000000000880]:addi a1, zero, 1
[0x80000000000884]:srli a0, a0, 12
[0x80000000000888]:slli a0, a0, 10
[0x8000000000088c]:or a0, a0, a1
[0x80000000000890]:addi zero, zero, 0
[0x80000000000894]:addi zero, zero, 0
[0x80000000000898]:addi zero, zero, 0
[0x8000000000089c]:addi zero, zero, 0
[0x800000000008a0]:auipc t1, 5
[0x800000000008a4]:addi t1, t1, 1888
[0x800000000008a8]:addi zero, zero, 0
[0x800000000008ac]:addi zero, zero, 0
[0x800000000008b0]:addi zero, zero, 0
[0x800000000008b4]:addi zero, zero, 0
[0x800000000008b8]:addi zero, zero, 0
[0x800000000008bc]:addi zero, zero, 0
[0x800000000008c0]:addi t0, zero, 320
[0x800000000008c4]:add t1, t1, t0
[0x800000000008c8]:sd a0, 0(t1)
[0x800000000008cc]:addi zero, zero, 0
[0x800000000008d0]:addi zero, zero, 0
[0x800000000008d4]:addi zero, zero, 0
[0x800000000008d8]:addi zero, zero, 0
[0x800000000008dc]:addi zero, zero, 0
[0x800000000008e0]:auipc a0, 4
[0x800000000008e4]:addi a0, a0, 1824
[0x800000000008e8]:addi zero, zero, 0
[0x800000000008ec]:addi zero, zero, 0
[0x800000000008f0]:addi zero, zero, 0
[0x800000000008f4]:addi zero, zero, 0
[0x800000000008f8]:addi zero, zero, 0
[0x800000000008fc]:addi zero, zero, 0
[0x80000000000900]:addi a1, zero, 1
[0x80000000000904]:srli a0, a0, 12
[0x80000000000908]:slli a0, a0, 10
[0x8000000000090c]:or a0, a0, a1
[0x80000000000910]:addi zero, zero, 0
[0x80000000000914]:addi zero, zero, 0
[0x80000000000918]:addi zero, zero, 0
[0x8000000000091c]:addi zero, zero, 0
[0x80000000000920]:auipc t1, 3
[0x80000000000924]:addi t1, t1, 1760
[0x80000000000928]:addi zero, zero, 0
[0x8000000000092c]:addi zero, zero, 0
[0x80000000000930]:addi zero, zero, 0
[0x80000000000934]:addi zero, zero, 0
[0x80000000000938]:addi zero, zero, 0
[0x8000000000093c]:addi zero, zero, 0
[0x80000000000940]:addi t0, zero, 0
[0x80000000000944]:add t1, t1, t0
[0x80000000000948]:sd a0, 0(t1)
[0x8000000000094c]:auipc a0, 6
[0x80000000000950]:addi a0, a0, 1988
[0x80000000000954]:addi a1, zero, 215
[0x80000000000958]:srli a0, a0, 12
[0x8000000000095c]:slli a0, a0, 10
[0x80000000000960]:or a0, a0, a1
[0x80000000000964]:addi zero, zero, 0
[0x80000000000968]:addi zero, zero, 0
[0x8000000000096c]:addi zero, zero, 0
[0x80000000000970]:addi zero, zero, 0
[0x80000000000974]:addi zero, zero, 0
[0x80000000000978]:addi zero, zero, 0
[0x8000000000097c]:addi zero, zero, 0
[0x80000000000980]:auipc t1, 4
[0x80000000000984]:addi t1, t1, 1664
[0x80000000000988]:addi zero, zero, 0
[0x8000000000098c]:addi zero, zero, 0
[0x80000000000990]:addi zero, zero, 0
[0x80000000000994]:addi zero, zero, 0
[0x80000000000998]:addi zero, zero, 0
[0x8000000000099c]:addi zero, zero, 0
[0x800000000009a0]:addi t0, zero, 0
[0x800000000009a4]:add t1, t1, t0
[0x800000000009a8]:sd a0, 0(t1)
[0x800000000009ac]:lui t0, 0
[0x800000000009b0]:addi t0, t0, 10
[0x800000000009b4]:slli t0, t0, 11
[0x800000000009b8]:addi t0, t0, 0
[0x800000000009bc]:slli t0, t0, 11
[0x800000000009c0]:addi t0, t0, 0
[0x800000000009c4]:slli t0, t0, 10
[0x800000000009c8]:addi t0, t0, 280
[0x800000000009cc]:addi zero, zero, 0
[0x800000000009d0]:addi zero, zero, 0
[0x800000000009d4]:addi zero, zero, 0
[0x800000000009d8]:addi zero, zero, 0
[0x800000000009dc]:addi zero, zero, 0
[0x800000000009e0]:auipc t1, 6
[0x800000000009e4]:addi t1, t1, 1840
[0x800000000009e8]:addi zero, zero, 0
[0x800000000009ec]:addi zero, zero, 0
[0x800000000009f0]:addi zero, zero, 0
[0x800000000009f4]:addi zero, zero, 0
[0x800000000009f8]:addi zero, zero, 0
[0x800000000009fc]:addi zero, zero, 0
[0x80000000000a00]:sub t0, t0, t1
[0x80000000000a04]:add s11, a3, t0
[0x80000000000a08]:addi zero, zero, 0
[0x80000000000a0c]:addi zero, zero, 0
[0x80000000000a10]:addi zero, zero, 0
[0x80000000000a14]:addi zero, zero, 0
[0x80000000000a18]:addi zero, zero, 0
[0x80000000000a1c]:addi zero, zero, 0
[0x80000000000a20]:auipc t6, 5
[0x80000000000a24]:addi t6, t6, 1504
[0x80000000000a28]:addi zero, zero, 0
[0x80000000000a2c]:addi zero, zero, 0
[0x80000000000a30]:addi zero, zero, 0
[0x80000000000a34]:addi zero, zero, 0
[0x80000000000a38]:addi zero, zero, 0
[0x80000000000a3c]:addi zero, zero, 0
[0x80000000000a40]:addi t5, zero, 4095
[0x80000000000a44]:slli t5, t5, 63
[0x80000000000a48]:srli t6, t6, 12
[0x80000000000a4c]:or t6, t6, t5
[0x80000000000a50]:csrrw zero, satp, t6
[0x80000000000a54]:addi t0, zero, 9
[0x80000000000a58]:slli t0, t0, 32
[0x80000000000a5c]:addi t1, zero, 1
[0x80000000000a60]:slli t1, t1, 55
[0x80000000000a64]:sub t0, t0, t1
[0x80000000000a68]:csrrs sp, mscratch, zero
[0x80000000000a6c]:add t1, sp, t0
[0x80000000000a70]:csrrw zero, sscratch, t1
[0x80000000000a74]:ld t1, 472(sp)
[0x80000000000a78]:add t2, t1, t0
[0x80000000000a7c]:sd t2, 1136(sp)
[0x80000000000a80]:sd t2, 1800(sp)
[0x80000000000a84]:lui t0, 0
[0x80000000000a88]:addi t0, t0, 9
[0x80000000000a8c]:slli t0, t0, 11
[0x80000000000a90]:addi t0, t0, 1024
[0x80000000000a94]:slli t0, t0, 11
[0x80000000000a98]:addi t0, t0, 1
[0x80000000000a9c]:slli t0, t0, 10
[0x80000000000aa0]:addi t0, t0, 648
[0x80000000000aa4]:addi zero, zero, 0
[0x80000000000aa8]:addi zero, zero, 0
[0x80000000000aac]:addi zero, zero, 0
[0x80000000000ab0]:addi zero, zero, 0
[0x80000000000ab4]:addi zero, zero, 0
[0x80000000000ab8]:addi zero, zero, 0
[0x80000000000abc]:addi zero, zero, 0
[0x80000000000ac0]:auipc t1, 0
[0x80000000000ac4]:addi t1, t1, 3016
[0x80000000000ac8]:addi zero, zero, 0
[0x80000000000acc]:addi zero, zero, 0
[0x80000000000ad0]:addi zero, zero, 0
[0x80000000000ad4]:addi zero, zero, 0
[0x80000000000ad8]:addi zero, zero, 0
[0x80000000000adc]:addi zero, zero, 0
[0x80000000000ae0]:sub t0, t0, t1
[0x80000000000ae4]:ld t1, 488(sp)
[0x80000000000ae8]:add t2, t1, t0
[0x80000000000aec]:sd t2, 1152(sp)
[0x80000000000af0]:sd t2, 1816(sp)
[0x80000000000af4]:lui t0, 0
[0x80000000000af8]:addi t0, t0, 10
[0x80000000000afc]:slli t0, t0, 11
[0x80000000000b00]:addi t0, t0, 0
[0x80000000000b04]:slli t0, t0, 11
[0x80000000000b08]:addi t0, t0, 0
[0x80000000000b0c]:slli t0, t0, 10
[0x80000000000b10]:addi t0, t0, 280
[0x80000000000b14]:addi zero, zero, 0
[0x80000000000b18]:addi zero, zero, 0
[0x80000000000b1c]:addi zero, zero, 0
[0x80000000000b20]:auipc t1, 6
[0x80000000000b24]:addi t1, t1, 1528
[0x80000000000b28]:addi zero, zero, 0
[0x80000000000b2c]:addi zero, zero, 0
[0x80000000000b30]:addi zero, zero, 0
[0x80000000000b34]:addi zero, zero, 0
[0x80000000000b38]:addi zero, zero, 0
[0x80000000000b3c]:addi zero, zero, 0
[0x80000000000b40]:sub t0, t0, t1
[0x80000000000b44]:ld t1, 504(sp)
[0x80000000000b48]:add t2, t1, t0
[0x80000000000b4c]:sd t2, 1168(sp)
[0x80000000000b50]:sd t2, 1832(sp)
[0x80000000000b54]:lui t0, 0
[0x80000000000b58]:addi t0, t0, 9
[0x80000000000b5c]:slli t0, t0, 11
[0x80000000000b60]:addi t0, t0, 1024
[0x80000000000b64]:slli t0, t0, 11
[0x80000000000b68]:addi t0, t0, 1
[0x80000000000b6c]:slli t0, t0, 10
[0x80000000000b70]:addi t0, t0, 648
[0x80000000000b74]:addi zero, zero, 0
[0x80000000000b78]:addi zero, zero, 0
[0x80000000000b7c]:addi zero, zero, 0
[0x80000000000b80]:auipc t1, 0
[0x80000000000b84]:addi t1, t1, 2824
[0x80000000000b88]:addi zero, zero, 0
[0x80000000000b8c]:addi zero, zero, 0
[0x80000000000b90]:addi zero, zero, 0
[0x80000000000b94]:addi zero, zero, 0
[0x80000000000b98]:addi zero, zero, 0
[0x80000000000b9c]:addi zero, zero, 0
[0x80000000000ba0]:sub t0, t0, t1
[0x80000000000ba4]:ld t1, 520(sp)
[0x80000000000ba8]:add t2, t1, t0
[0x80000000000bac]:sd t2, 1184(sp)
[0x80000000000bb0]:sd t2, 1848(sp)
[0x80000000000bb4]:sfence.vma zero, zero
[0x80000000000bb8]:addi s1, zero, 4095
[0x80000000000bbc]:srli s1, s1, 62
[0x80000000000bc0]:slli s1, s1, 11
[0x80000000000bc4]:csrrc zero, mstatus, s1
[0x80000000000bc8]:csrrs sp, mscratch, zero
[0x80000000000bcc]:ld t1, 1800(sp)
[0x80000000000bd0]:ld s1, 472(sp)
[0x80000000000bd4]:sub t1, t1, s1
[0x80000000000bd8]:addi t1, t1, 16
[0x80000000000bdc]:auipc s1, 0
[0x80000000000be0]:add s1, s1, t1
[0x80000000000be4]:csrrw s1, mepc, s1
[0x80000000000be8]:mret
[0x80000000000d80]:jal zero, 256
[0x80000000000e80]:csrrw sp, mscratch, sp
[0x80000000000e84]:sd a1, 648(sp)
[0x80000000000e88]:jal a1, 184
[0x80000000000f40]:sd a0, 640(sp)
[0x80000000000f44]:csrrw a0, mscratch, sp
[0x80000000000f48]:sd a0, 656(sp)
[0x80000000000f4c]:ld a0, 560(sp)
[0x80000000000f50]:jalr zero, a0, 0
[0x80000000000f54]:sd s1, 632(sp)
[0x80000000000f58]:sd fp, 624(sp)
[0x80000000000f5c]:sd t2, 616(sp)
[0x80000000000f60]:sd t1, 608(sp)
[0x80000000000f64]:csrrs a0, mcause, zero
[0x80000000000f68]:addi s1, a0, 4088
[0x80000000000f6c]:andi s1, s1, 4092
[0x80000000000f70]:bne s1, zero, 12
[0x80000000000f7c]:addi t2, zero, 32
[0x80000000000f80]:bge a0, zero, 68
[0x80000000000fc4]:csrrs t1, misa, zero
[0x80000000000fc8]:slli t1, t1, 56
[0x80000000000fcc]:bge t1, zero, 8
[0x80000000000fd4]:ld t1, 536(sp)
[0x80000000000fd8]:add s1, t1, t2
[0x80000000000fdc]:sd s1, 536(sp)
[0x80000000000fe0]:ld fp, 576(sp)
[0x80000000000fe4]:sub a1, a1, fp
[0x80000000000fe8]:slli a1, a1, 4
[0x80000000000fec]:or a1, a1, t2
[0x80000000000ff0]:addi a1, a1, 3
[0x80000000000ff4]:sd a1, 0(t1)
[0x80000000000ff8]:sd a0, 8(t1)
[0x80000000000ffc]:blt a0, zero, 324
[0x80000000001000]:addi s1, sp, 0
[0x80000000001004]:csrrs a1, mstatus, zero
[0x80000000001008]:slli fp, a1, 51
[0x8000000000100c]:blt fp, zero, 24
[0x80000000001010]:addi s1, s1, 664
[0x80000000001014]:srli a1, a1, 32
[0x80000000001018]:slli a1, a1, 24
[0x8000000000101c]:bge a1, zero, 8
[0x80000000001024]:csrrs t2, mepc, zero
[0x80000000001028]:ld fp, 520(s1)
[0x8000000000102c]:ld a1, 528(s1)
[0x80000000001030]:add a1, a1, fp
[0x80000000001034]:bgeu t2, a1, 8
[0x80000000001038]:bgeu t2, fp, 44
[0x8000000000103c]:ld fp, 472(s1)
[0x80000000001040]:ld a1, 480(s1)
[0x80000000001044]:add a1, a1, fp
[0x80000000001048]:bgeu t2, a1, 8
[0x8000000000104c]:bgeu t2, fp, 24
[0x80000000001064]:sub fp, t2, fp
[0x80000000001068]:sd fp, 16(t1)
[0x8000000000106c]:andi a1, t2, 4092
[0x80000000001070]:addi a1, a1, 8
[0x80000000001074]:csrrw zero, mepc, a1
[0x80000000001078]:csrrs t2, mtval, zero
[0x8000000000107c]:andi a0, a0, 15
[0x80000000001080]:lui fp, 0
[0x80000000001084]:addi fp, fp, 0
[0x80000000001088]:slli fp, fp, 11
[0x8000000000108c]:addi fp, fp, 0
[0x80000000001090]:slli fp, fp, 11
[0x80000000001094]:addi fp, fp, 44
[0x80000000001098]:slli fp, fp, 10
[0x8000000000109c]:addi fp, fp, 251
[0x800000000010a0]:srl fp, fp, a0
[0x800000000010a4]:slli fp, fp, 63
[0x800000000010a8]:bge fp, zero, 88
[0x800000000010ac]:ld fp, 520(s1)
[0x800000000010b0]:ld a1, 528(s1)
[0x800000000010b4]:add a1, a1, fp
[0x800000000010b8]:bgeu t2, a1, 8
[0x800000000010bc]:bgeu t2, fp, 64
[0x800000000010c0]:ld fp, 504(s1)
[0x800000000010c4]:ld a1, 512(s1)
[0x800000000010c8]:add a1, a1, fp
[0x800000000010cc]:bgeu t2, a1, 8
[0x800000000010d0]:bgeu t2, fp, 44
[0x800000000010d4]:ld fp, 472(s1)
[0x800000000010d8]:ld a1, 480(s1)
[0x800000000010dc]:add a1, a1, fp
[0x800000000010e0]:bgeu t2, a1, 8
[0x800000000010e4]:bgeu t2, fp, 24
[0x800000000010fc]:sub fp, t2, fp
[0x80000000001100]:sd fp, 24(t1)
[0x80000000001104]:ld s1, 536(sp)
[0x80000000001108]:ld t2, 504(sp)
[0x8000000000110c]:ld t1, 512(sp)
[0x80000000001110]:add t1, t1, t2
[0x80000000001114]:bltu t1, s1, 7036
[0x80000000001118]:addi t2, zero, 512
[0x8000000000111c]:jal zero, 64
[0x8000000000115c]:auipc fp, 0
[0x80000000001160]:addi fp, fp, 60
[0x80000000001164]:add fp, fp, t2
[0x80000000001168]:slli t2, a0, 3
[0x8000000000116c]:add fp, fp, t2
[0x80000000001170]:andi fp, fp, 4088
[0x80000000001174]:ld fp, 0(fp)
[0x80000000001178]:beq fp, zero, 7084
[0x8000000000117c]:slli t2, fp, 63
[0x80000000001180]:bge t2, zero, 16
[0x80000000001184]:srli fp, fp, 1
[0x80000000001188]:beq a0, fp, 8088
[0x80000000001120]:ld t1, 608(sp)
[0x80000000001124]:ld t2, 616(sp)
[0x80000000001128]:ld fp, 624(sp)
[0x8000000000112c]:ld s1, 632(sp)
[0x80000000001130]:ld a0, 640(sp)
[0x80000000001134]:ld a1, 648(sp)
[0x80000000001138]:ld sp, 656(sp)
[0x8000000000113c]:mret
[0x900000bf4]:lui a4, 0
[0x900000bf8]:addi a4, a4, 0
[0x900000bfc]:slli a4, a4, 11
[0x900000c00]:addi a4, a4, 0
[0x900000c04]:slli a4, a4, 11
[0x900000c08]:addi a4, a4, 55
[0x900000c0c]:slli a4, a4, 10
[0x900000c10]:addi a4, a4, 685
[0x900000c14]:sd a4, 16(s11)
[0x900000c18]:addi zero, zero, 0
[0x900000c1c]:lui t0, 0
[0x900000c20]:addi t0, t0, 9
[0x900000c24]:slli t0, t0, 11
[0x900000c28]:addi t0, t0, 1024
[0x900000c2c]:slli t0, t0, 11
[0x900000c30]:addi t0, t0, 1
[0x900000c34]:slli t0, t0, 10
[0x900000c38]:addi t0, t0, 648
[0x900000c3c]:ld t0, 0(t0)

[0x80000000000bc4]:csrrc zero, mstatus, s1
[0x80000000000bc8]:csrrs sp, mscratch, zero
[0x80000000000bcc]:ld t1, 1800(sp)
[0x80000000000bd0]:ld s1, 472(sp)
[0x80000000000bd4]:sub t1, t1, s1
[0x80000000000bd8]:addi t1, t1, 16
[0x80000000000bdc]:auipc s1, 0
[0x80000000000be0]:add s1, s1, t1
[0x80000000000be4]:csrrw s1, mepc, s1
[0x80000000000be8]:mret
[0x80000000000d80]:jal zero, 256
[0x80000000000e80]:csrrw sp, mscratch, sp
[0x80000000000e84]:sd a1, 648(sp)
[0x80000000000e88]:jal a1, 184
[0x80000000000f40]:sd a0, 640(sp)
[0x80000000000f44]:csrrw a0, mscratch, sp
[0x80000000000f48]:sd a0, 656(sp)
[0x80000000000f4c]:ld a0, 560(sp)
[0x80000000000f50]:jalr zero, a0, 0
[0x80000000000f54]:sd s1, 632(sp)
[0x80000000000f58]:sd fp, 624(sp)
[0x80000000000f5c]:sd t2, 616(sp)
[0x80000000000f60]:sd t1, 608(sp)
[0x80000000000f64]:csrrs a0, mcause, zero
[0x80000000000f68]:addi s1, a0, 4088
[0x80000000000f6c]:andi s1, s1, 4092
[0x80000000000f70]:bne s1, zero, 12
[0x80000000000f7c]:addi t2, zero, 32
[0x80000000000f80]:bge a0, zero, 68
[0x80000000000fc4]:csrrs t1, misa, zero
[0x80000000000fc8]:slli t1, t1, 56
[0x80000000000fcc]:bge t1, zero, 8
[0x80000000000fd4]:ld t1, 536(sp)
[0x80000000000fd8]:add s1, t1, t2
[0x80000000000fdc]:sd s1, 536(sp)
[0x80000000000fe0]:ld fp, 576(sp)
[0x80000000000fe4]:sub a1, a1, fp
[0x80000000000fe8]:slli a1, a1, 4
[0x80000000000fec]:or a1, a1, t2
[0x80000000000ff0]:addi a1, a1, 3
[0x80000000000ff4]:sd a1, 0(t1)
[0x80000000000ff8]:sd a0, 8(t1)
[0x80000000000ffc]:blt a0, zero, 324
[0x80000000001000]:addi s1, sp, 0
[0x80000000001004]:csrrs a1, mstatus, zero
[0x80000000001008]:slli fp, a1, 51
[0x8000000000100c]:blt fp, zero, 24
[0x80000000001010]:addi s1, s1, 664
[0x80000000001014]:srli a1, a1, 32
[0x80000000001018]:slli a1, a1, 24
[0x8000000000101c]:bge a1, zero, 8
[0x80000000001024]:csrrs t2, mepc, zero
[0x80000000001028]:ld fp, 520(s1)
[0x8000000000102c]:ld a1, 528(s1)
[0x80000000001030]:add a1, a1, fp
[0x80000000001034]:bgeu t2, a1, 8
[0x80000000001038]:bgeu t2, fp, 44
[0x8000000000103c]:ld fp, 472(s1)
[0x80000000001040]:ld a1, 480(s1)
[0x80000000001044]:add a1, a1, fp
[0x80000000001048]:bgeu t2, a1, 8
[0x8000000000104c]:bgeu t2, fp, 24
[0x80000000001064]:sub fp, t2, fp
[0x80000000001068]:sd fp, 16(t1)
[0x8000000000106c]:andi a1, t2, 4092
[0x80000000001070]:addi a1, a1, 8
[0x80000000001074]:csrrw zero, mepc, a1
[0x80000000001078]:csrrs t2, mtval, zero
[0x8000000000107c]:andi a0, a0, 15
[0x80000000001080]:lui fp, 0
[0x80000000001084]:addi fp, fp, 0
[0x80000000001088]:slli fp, fp, 11
[0x8000000000108c]:addi fp, fp, 0
[0x80000000001090]:slli fp, fp, 11
[0x80000000001094]:addi fp, fp, 44
[0x80000000001098]:slli fp, fp, 10
[0x8000000000109c]:addi fp, fp, 251
[0x800000000010a0]:srl fp, fp, a0
[0x800000000010a4]:slli fp, fp, 63
[0x800000000010a8]:bge fp, zero, 88
[0x800000000010ac]:ld fp, 520(s1)
[0x800000000010b0]:ld a1, 528(s1)
[0x800000000010b4]:add a1, a1, fp
[0x800000000010b8]:bgeu t2, a1, 8
[0x800000000010bc]:bgeu t2, fp, 64
[0x800000000010c0]:ld fp, 504(s1)
[0x800000000010c4]:ld a1, 512(s1)
[0x800000000010c8]:add a1, a1, fp
[0x800000000010cc]:bgeu t2, a1, 8
[0x800000000010d0]:bgeu t2, fp, 44
[0x800000000010d4]:ld fp, 472(s1)
[0x800000000010d8]:ld a1, 480(s1)
[0x800000000010dc]:add a1, a1, fp
[0x800000000010e0]:bgeu t2, a1, 8
[0x800000000010e4]:bgeu t2, fp, 24
[0x800000000010fc]:sub fp, t2, fp
[0x80000000001100]:sd fp, 24(t1)
[0x80000000001104]:ld s1, 536(sp)
[0x80000000001108]:ld t2, 504(sp)
[0x8000000000110c]:ld t1, 512(sp)
[0x80000000001110]:add t1, t1, t2
[0x80000000001114]:bltu t1, s1, 7036
[0x80000000001118]:addi t2, zero, 512
[0x8000000000111c]:jal zero, 64
[0x8000000000115c]:auipc fp, 0
[0x80000000001160]:addi fp, fp, 60
[0x80000000001164]:add fp, fp, t2
[0x80000000001168]:slli t2, a0, 3
[0x8000000000116c]:add fp, fp, t2
[0x80000000001170]:andi fp, fp, 4088
[0x80000000001174]:ld fp, 0(fp)
[0x80000000001178]:beq fp, zero, 7084
[0x8000000000117c]:slli t2, fp, 63
[0x80000000001180]:bge t2, zero, 16
[0x80000000001184]:srli fp, fp, 1
[0x80000000001188]:beq a0, fp, 8088
[0x80000000001120]:ld t1, 608(sp)
[0x80000000001124]:ld t2, 616(sp)
[0x80000000001128]:ld fp, 624(sp)
[0x8000000000112c]:ld s1, 632(sp)
[0x80000000001130]:ld a0, 640(sp)
[0x80000000001134]:ld a1, 648(sp)
[0x80000000001138]:ld sp, 656(sp)
[0x8000000000113c]:mret
[0x900000bf4]:lui a4, 0
[0x900000bf8]:addi a4, a4, 0
[0x900000bfc]:slli a4, a4, 11
[0x900000c00]:addi a4, a4, 0
[0x900000c04]:slli a4, a4, 11
[0x900000c08]:addi a4, a4, 55
[0x900000c0c]:slli a4, a4, 10
[0x900000c10]:addi a4, a4, 685
[0x900000c14]:sd a4, 16(s11)
[0x900000c18]:addi zero, zero, 0
[0x900000c1c]:lui t0, 0
[0x900000c20]:addi t0, t0, 9
[0x900000c24]:slli t0, t0, 11
[0x900000c28]:addi t0, t0, 1024
[0x900000c2c]:slli t0, t0, 11
[0x900000c30]:addi t0, t0, 1
[0x900000c34]:slli t0, t0, 10
[0x900000c38]:addi t0, t0, 648
[0x900000c3c]:ld t0, 0(t0)

[0x80000000000ff8]:sd a0, 8(t1)
[0x80000000000ffc]:blt a0, zero, 324
[0x80000000001000]:addi s1, sp, 0
[0x80000000001004]:csrrs a1, mstatus, zero

[0x80000000000ff8]:sd a0, 8(t1)
[0x80000000000ffc]:blt a0, zero, 324
[0x80000000001000]:addi s1, sp, 0
[0x80000000001004]:csrrs a1, mstatus, zero

[0x80000000000a50]:csrrw zero, satp, t6
[0x80000000000a54]:addi t0, zero, 9
[0x80000000000a58]:slli t0, t0, 32
[0x80000000000a5c]:addi t1, zero, 1
[0x80000000000a60]:slli t1, t1, 55
[0x80000000000a64]:sub t0, t0, t1
[0x80000000000a68]:csrrs sp, mscratch, zero
[0x80000000000a6c]:add t1, sp, t0
[0x80000000000a70]:csrrw zero, sscratch, t1
[0x80000000000a74]:ld t1, 472(sp)
[0x80000000000a78]:add t2, t1, t0
[0x80000000000a7c]:sd t2, 1136(sp)
[0x80000000000a80]:sd t2, 1800(sp)
[0x80000000000a84]:lui t0, 0
[0x80000000000a88]:addi t0, t0, 9
[0x80000000000a8c]:slli t0, t0, 11
[0x80000000000a90]:addi t0, t0, 1024
[0x80000000000a94]:slli t0, t0, 11
[0x80000000000a98]:addi t0, t0, 1
[0x80000000000a9c]:slli t0, t0, 10
[0x80000000000aa0]:addi t0, t0, 648
[0x80000000000aa4]:addi zero, zero, 0
[0x80000000000aa8]:addi zero, zero, 0
[0x80000000000aac]:addi zero, zero, 0
[0x80000000000ab0]:addi zero, zero, 0
[0x80000000000ab4]:addi zero, zero, 0
[0x80000000000ab8]:addi zero, zero, 0
[0x80000000000abc]:addi zero, zero, 0
[0x80000000000ac0]:auipc t1, 0
[0x80000000000ac4]:addi t1, t1, 3016
[0x80000000000ac8]:addi zero, zero, 0
[0x80000000000acc]:addi zero, zero, 0
[0x80000000000ad0]:addi zero, zero, 0
[0x80000000000ad4]:addi zero, zero, 0
[0x80000000000ad8]:addi zero, zero, 0
[0x80000000000adc]:addi zero, zero, 0
[0x80000000000ae0]:sub t0, t0, t1
[0x80000000000ae4]:ld t1, 488(sp)
[0x80000000000ae8]:add t2, t1, t0
[0x80000000000aec]:sd t2, 1152(sp)
[0x80000000000af0]:sd t2, 1816(sp)
[0x80000000000af4]:lui t0, 0
[0x80000000000af8]:addi t0, t0, 10
[0x80000000000afc]:slli t0, t0, 11
[0x80000000000b00]:addi t0, t0, 0
[0x80000000000b04]:slli t0, t0, 11
[0x80000000000b08]:addi t0, t0, 0
[0x80000000000b0c]:slli t0, t0, 10
[0x80000000000b10]:addi t0, t0, 280
[0x80000000000b14]:addi zero, zero, 0
[0x80000000000b18]:addi zero, zero, 0
[0x80000000000b1c]:addi zero, zero, 0
[0x80000000000b20]:auipc t1, 6
[0x80000000000b24]:addi t1, t1, 1528
[0x80000000000b28]:addi zero, zero, 0
[0x80000000000b2c]:addi zero, zero, 0
[0x80000000000b30]:addi zero, zero, 0
[0x80000000000b34]:addi zero, zero, 0
[0x80000000000b38]:addi zero, zero, 0
[0x80000000000b3c]:addi zero, zero, 0
[0x80000000000b40]:sub t0, t0, t1
[0x80000000000b44]:ld t1, 504(sp)
[0x80000000000b48]:add t2, t1, t0
[0x80000000000b4c]:sd t2, 1168(sp)
[0x80000000000b50]:sd t2, 1832(sp)
[0x80000000000b54]:lui t0, 0
[0x80000000000b58]:addi t0, t0, 9
[0x80000000000b5c]:slli t0, t0, 11
[0x80000000000b60]:addi t0, t0, 1024
[0x80000000000b64]:slli t0, t0, 11
[0x80000000000b68]:addi t0, t0, 1
[0x80000000000b6c]:slli t0, t0, 10
[0x80000000000b70]:addi t0, t0, 648
[0x80000000000b74]:addi zero, zero, 0
[0x80000000000b78]:addi zero, zero, 0
[0x80000000000b7c]:addi zero, zero, 0
[0x80000000000b80]:auipc t1, 0
[0x80000000000b84]:addi t1, t1, 2824
[0x80000000000b88]:addi zero, zero, 0
[0x80000000000b8c]:addi zero, zero, 0
[0x80000000000b90]:addi zero, zero, 0
[0x80000000000b94]:addi zero, zero, 0
[0x80000000000b98]:addi zero, zero, 0
[0x80000000000b9c]:addi zero, zero, 0
[0x80000000000ba0]:sub t0, t0, t1
[0x80000000000ba4]:ld t1, 520(sp)
[0x80000000000ba8]:add t2, t1, t0
[0x80000000000bac]:sd t2, 1184(sp)
[0x80000000000bb0]:sd t2, 1848(sp)
[0x80000000000bb4]:sfence.vma zero, zero
[0x80000000000bb8]:addi s1, zero, 4095
[0x80000000000bbc]:srli s1, s1, 62
[0x80000000000bc0]:slli s1, s1, 11
[0x80000000000bc4]:csrrc zero, mstatus, s1
[0x80000000000bc8]:csrrs sp, mscratch, zero
[0x80000000000bcc]:ld t1, 1800(sp)
[0x80000000000bd0]:ld s1, 472(sp)
[0x80000000000bd4]:sub t1, t1, s1
[0x80000000000bd8]:addi t1, t1, 16
[0x80000000000bdc]:auipc s1, 0
[0x80000000000be0]:add s1, s1, t1
[0x80000000000be4]:csrrw s1, mepc, s1
[0x80000000000be8]:mret
[0x80000000000d80]:jal zero, 256
[0x80000000000e80]:csrrw sp, mscratch, sp
[0x80000000000e84]:sd a1, 648(sp)
[0x80000000000e88]:jal a1, 184
[0x80000000000f40]:sd a0, 640(sp)
[0x80000000000f44]:csrrw a0, mscratch, sp
[0x80000000000f48]:sd a0, 656(sp)
[0x80000000000f4c]:ld a0, 560(sp)
[0x80000000000f50]:jalr zero, a0, 0
[0x80000000000f54]:sd s1, 632(sp)
[0x80000000000f58]:sd fp, 624(sp)
[0x80000000000f5c]:sd t2, 616(sp)
[0x80000000000f60]:sd t1, 608(sp)
[0x80000000000f64]:csrrs a0, mcause, zero
[0x80000000000f68]:addi s1, a0, 4088
[0x80000000000f6c]:andi s1, s1, 4092
[0x80000000000f70]:bne s1, zero, 12
[0x80000000000f7c]:addi t2, zero, 32
[0x80000000000f80]:bge a0, zero, 68
[0x80000000000fc4]:csrrs t1, misa, zero
[0x80000000000fc8]:slli t1, t1, 56
[0x80000000000fcc]:bge t1, zero, 8
[0x80000000000fd4]:ld t1, 536(sp)
[0x80000000000fd8]:add s1, t1, t2
[0x80000000000fdc]:sd s1, 536(sp)
[0x80000000000fe0]:ld fp, 576(sp)
[0x80000000000fe4]:sub a1, a1, fp
[0x80000000000fe8]:slli a1, a1, 4
[0x80000000000fec]:or a1, a1, t2
[0x80000000000ff0]:addi a1, a1, 3
[0x80000000000ff4]:sd a1, 0(t1)
[0x80000000000ff8]:sd a0, 8(t1)
[0x80000000000ffc]:blt a0, zero, 324
[0x80000000001000]:addi s1, sp, 0
[0x80000000001004]:csrrs a1, mstatus, zero
[0x80000000001008]:slli fp, a1, 51
[0x8000000000100c]:blt fp, zero, 24
[0x80000000001010]:addi s1, s1, 664
[0x80000000001014]:srli a1, a1, 32
[0x80000000001018]:slli a1, a1, 24
[0x8000000000101c]:bge a1, zero, 8
[0x80000000001024]:csrrs t2, mepc, zero
[0x80000000001028]:ld fp, 520(s1)
[0x8000000000102c]:ld a1, 528(s1)
[0x80000000001030]:add a1, a1, fp
[0x80000000001034]:bgeu t2, a1, 8
[0x80000000001038]:bgeu t2, fp, 44
[0x8000000000103c]:ld fp, 472(s1)
[0x80000000001040]:ld a1, 480(s1)
[0x80000000001044]:add a1, a1, fp
[0x80000000001048]:bgeu t2, a1, 8
[0x8000000000104c]:bgeu t2, fp, 24
[0x80000000001064]:sub fp, t2, fp
[0x80000000001068]:sd fp, 16(t1)
[0x8000000000106c]:andi a1, t2, 4092
[0x80000000001070]:addi a1, a1, 8
[0x80000000001074]:csrrw zero, mepc, a1
[0x80000000001078]:csrrs t2, mtval, zero
[0x8000000000107c]:andi a0, a0, 15
[0x80000000001080]:lui fp, 0
[0x80000000001084]:addi fp, fp, 0
[0x80000000001088]:slli fp, fp, 11
[0x8000000000108c]:addi fp, fp, 0
[0x80000000001090]:slli fp, fp, 11
[0x80000000001094]:addi fp, fp, 44
[0x80000000001098]:slli fp, fp, 10
[0x8000000000109c]:addi fp, fp, 251
[0x800000000010a0]:srl fp, fp, a0
[0x800000000010a4]:slli fp, fp, 63
[0x800000000010a8]:bge fp, zero, 88
[0x800000000010ac]:ld fp, 520(s1)
[0x800000000010b0]:ld a1, 528(s1)
[0x800000000010b4]:add a1, a1, fp
[0x800000000010b8]:bgeu t2, a1, 8
[0x800000000010bc]:bgeu t2, fp, 64
[0x800000000010c0]:ld fp, 504(s1)
[0x800000000010c4]:ld a1, 512(s1)
[0x800000000010c8]:add a1, a1, fp
[0x800000000010cc]:bgeu t2, a1, 8
[0x800000000010d0]:bgeu t2, fp, 44
[0x800000000010d4]:ld fp, 472(s1)
[0x800000000010d8]:ld a1, 480(s1)
[0x800000000010dc]:add a1, a1, fp
[0x800000000010e0]:bgeu t2, a1, 8
[0x800000000010e4]:bgeu t2, fp, 24
[0x800000000010fc]:sub fp, t2, fp
[0x80000000001100]:sd fp, 24(t1)
[0x80000000001104]:ld s1, 536(sp)
[0x80000000001108]:ld t2, 504(sp)
[0x8000000000110c]:ld t1, 512(sp)
[0x80000000001110]:add t1, t1, t2
[0x80000000001114]:bltu t1, s1, 7036
[0x80000000001118]:addi t2, zero, 512
[0x8000000000111c]:jal zero, 64
[0x8000000000115c]:auipc fp, 0
[0x80000000001160]:addi fp, fp, 60
[0x80000000001164]:add fp, fp, t2
[0x80000000001168]:slli t2, a0, 3
[0x8000000000116c]:add fp, fp, t2
[0x80000000001170]:andi fp, fp, 4088
[0x80000000001174]:ld fp, 0(fp)
[0x80000000001178]:beq fp, zero, 7084
[0x8000000000117c]:slli t2, fp, 63
[0x80000000001180]:bge t2, zero, 16
[0x80000000001184]:srli fp, fp, 1
[0x80000000001188]:beq a0, fp, 8088
[0x80000000001120]:ld t1, 608(sp)
[0x80000000001124]:ld t2, 616(sp)
[0x80000000001128]:ld fp, 624(sp)
[0x8000000000112c]:ld s1, 632(sp)
[0x80000000001130]:ld a0, 640(sp)
[0x80000000001134]:ld a1, 648(sp)
[0x80000000001138]:ld sp, 656(sp)
[0x8000000000113c]:mret
[0x900000bf4]:lui a4, 0
[0x900000bf8]:addi a4, a4, 0
[0x900000bfc]:slli a4, a4, 11
[0x900000c00]:addi a4, a4, 0
[0x900000c04]:slli a4, a4, 11
[0x900000c08]:addi a4, a4, 55
[0x900000c0c]:slli a4, a4, 10
[0x900000c10]:addi a4, a4, 685
[0x900000c14]:sd a4, 16(s11)
[0x900000c18]:addi zero, zero, 0
[0x900000c1c]:lui t0, 0
[0x900000c20]:addi t0, t0, 9
[0x900000c24]:slli t0, t0, 11
[0x900000c28]:addi t0, t0, 1024
[0x900000c2c]:slli t0, t0, 11
[0x900000c30]:addi t0, t0, 1
[0x900000c34]:slli t0, t0, 10
[0x900000c38]:addi t0, t0, 648
[0x900000c3c]:ld t0, 0(t0)
[0x80000000000d80]:jal zero, 256
[0x80000000000e80]:csrrw sp, mscratch, sp
[0x80000000000e84]:sd a1, 648(sp)
[0x80000000000e88]:jal a1, 184
[0x80000000000f40]:sd a0, 640(sp)
[0x80000000000f44]:csrrw a0, mscratch, sp
[0x80000000000f48]:sd a0, 656(sp)
[0x80000000000f4c]:ld a0, 560(sp)
[0x80000000000f50]:jalr zero, a0, 0
[0x80000000000f54]:sd s1, 632(sp)
[0x80000000000f58]:sd fp, 624(sp)
[0x80000000000f5c]:sd t2, 616(sp)
[0x80000000000f60]:sd t1, 608(sp)
[0x80000000000f64]:csrrs a0, mcause, zero
[0x80000000000f68]:addi s1, a0, 4088
[0x80000000000f6c]:andi s1, s1, 4092
[0x80000000000f70]:bne s1, zero, 12
[0x80000000000f7c]:addi t2, zero, 32
[0x80000000000f80]:bge a0, zero, 68
[0x80000000000fc4]:csrrs t1, misa, zero
[0x80000000000fc8]:slli t1, t1, 56
[0x80000000000fcc]:bge t1, zero, 8
[0x80000000000fd4]:ld t1, 536(sp)
[0x80000000000fd8]:add s1, t1, t2
[0x80000000000fdc]:sd s1, 536(sp)
[0x80000000000fe0]:ld fp, 576(sp)
[0x80000000000fe4]:sub a1, a1, fp
[0x80000000000fe8]:slli a1, a1, 4
[0x80000000000fec]:or a1, a1, t2
[0x80000000000ff0]:addi a1, a1, 3
[0x80000000000ff4]:sd a1, 0(t1)
[0x80000000000ff8]:sd a0, 8(t1)
[0x80000000000ffc]:blt a0, zero, 324
[0x80000000001000]:addi s1, sp, 0
[0x80000000001004]:csrrs a1, mstatus, zero
[0x80000000001008]:slli fp, a1, 51
[0x8000000000100c]:blt fp, zero, 24
[0x80000000001010]:addi s1, s1, 664
[0x80000000001014]:srli a1, a1, 32
[0x80000000001018]:slli a1, a1, 24
[0x8000000000101c]:bge a1, zero, 8
[0x80000000001024]:csrrs t2, mepc, zero
[0x80000000001028]:ld fp, 520(s1)
[0x8000000000102c]:ld a1, 528(s1)
[0x80000000001030]:add a1, a1, fp
[0x80000000001034]:bgeu t2, a1, 8
[0x80000000001038]:bgeu t2, fp, 44
[0x8000000000103c]:ld fp, 472(s1)
[0x80000000001040]:ld a1, 480(s1)
[0x80000000001044]:add a1, a1, fp
[0x80000000001048]:bgeu t2, a1, 8
[0x8000000000104c]:bgeu t2, fp, 24
[0x80000000001064]:sub fp, t2, fp
[0x80000000001068]:sd fp, 16(t1)
[0x8000000000106c]:andi a1, t2, 4092
[0x80000000001070]:addi a1, a1, 8
[0x80000000001074]:csrrw zero, mepc, a1
[0x80000000001078]:csrrs t2, mtval, zero
[0x8000000000107c]:andi a0, a0, 15
[0x80000000001080]:lui fp, 0
[0x80000000001084]:addi fp, fp, 0
[0x80000000001088]:slli fp, fp, 11
[0x8000000000108c]:addi fp, fp, 0
[0x80000000001090]:slli fp, fp, 11
[0x80000000001094]:addi fp, fp, 44
[0x80000000001098]:slli fp, fp, 10
[0x8000000000109c]:addi fp, fp, 251
[0x800000000010a0]:srl fp, fp, a0
[0x800000000010a4]:slli fp, fp, 63
[0x800000000010a8]:bge fp, zero, 88
[0x800000000010ac]:ld fp, 520(s1)
[0x800000000010b0]:ld a1, 528(s1)
[0x800000000010b4]:add a1, a1, fp
[0x800000000010b8]:bgeu t2, a1, 8
[0x800000000010bc]:bgeu t2, fp, 64
[0x800000000010fc]:sub fp, t2, fp
[0x80000000001100]:sd fp, 24(t1)
[0x80000000001104]:ld s1, 536(sp)
[0x80000000001108]:ld t2, 504(sp)
[0x8000000000110c]:ld t1, 512(sp)
[0x80000000001110]:add t1, t1, t2
[0x80000000001114]:bltu t1, s1, 7036
[0x80000000001118]:addi t2, zero, 512
[0x8000000000111c]:jal zero, 64
[0x8000000000115c]:auipc fp, 0
[0x80000000001160]:addi fp, fp, 60
[0x80000000001164]:add fp, fp, t2
[0x80000000001168]:slli t2, a0, 3
[0x8000000000116c]:add fp, fp, t2
[0x80000000001170]:andi fp, fp, 4088
[0x80000000001174]:ld fp, 0(fp)
[0x80000000001178]:beq fp, zero, 7084
[0x8000000000117c]:slli t2, fp, 63
[0x80000000001180]:bge t2, zero, 16
[0x80000000001184]:srli fp, fp, 1
[0x80000000001188]:beq a0, fp, 8088
[0x80000000001120]:ld t1, 608(sp)
[0x80000000001124]:ld t2, 616(sp)
[0x80000000001128]:ld fp, 624(sp)
[0x8000000000112c]:ld s1, 632(sp)
[0x80000000001130]:ld a0, 640(sp)
[0x80000000001134]:ld a1, 648(sp)
[0x80000000001138]:ld sp, 656(sp)
[0x8000000000113c]:mret
[0x900000c44]:sd sp, 0(t0)
[0x80000000000d80]:jal zero, 256
[0x80000000000e80]:csrrw sp, mscratch, sp
[0x80000000000e84]:sd a1, 648(sp)
[0x80000000000e88]:jal a1, 184
[0x80000000000f40]:sd a0, 640(sp)
[0x80000000000f44]:csrrw a0, mscratch, sp
[0x80000000000f48]:sd a0, 656(sp)
[0x80000000000f4c]:ld a0, 560(sp)
[0x80000000000f50]:jalr zero, a0, 0
[0x80000000000f54]:sd s1, 632(sp)
[0x80000000000f58]:sd fp, 624(sp)
[0x80000000000f5c]:sd t2, 616(sp)
[0x80000000000f60]:sd t1, 608(sp)
[0x80000000000f64]:csrrs a0, mcause, zero
[0x80000000000f68]:addi s1, a0, 4088
[0x80000000000f6c]:andi s1, s1, 4092
[0x80000000000f70]:bne s1, zero, 12
[0x80000000000f7c]:addi t2, zero, 32
[0x80000000000f80]:bge a0, zero, 68
[0x80000000000fc4]:csrrs t1, misa, zero
[0x80000000000fc8]:slli t1, t1, 56
[0x80000000000fcc]:bge t1, zero, 8
[0x80000000000fd4]:ld t1, 536(sp)
[0x80000000000fd8]:add s1, t1, t2
[0x80000000000fdc]:sd s1, 536(sp)
[0x80000000000fe0]:ld fp, 576(sp)
[0x80000000000fe4]:sub a1, a1, fp
[0x80000000000fe8]:slli a1, a1, 4
[0x80000000000fec]:or a1, a1, t2
[0x80000000000ff0]:addi a1, a1, 3
[0x80000000000ff4]:sd a1, 0(t1)
[0x80000000000ff8]:sd a0, 8(t1)
[0x80000000000ffc]:blt a0, zero, 324
[0x80000000001000]:addi s1, sp, 0
[0x80000000001004]:csrrs a1, mstatus, zero
[0x80000000001008]:slli fp, a1, 51
[0x8000000000100c]:blt fp, zero, 24
[0x80000000001010]:addi s1, s1, 664
[0x80000000001014]:srli a1, a1, 32
[0x80000000001018]:slli a1, a1, 24
[0x8000000000101c]:bge a1, zero, 8
[0x80000000001024]:csrrs t2, mepc, zero
[0x80000000001028]:ld fp, 520(s1)
[0x8000000000102c]:ld a1, 528(s1)
[0x80000000001030]:add a1, a1, fp
[0x80000000001034]:bgeu t2, a1, 8
[0x80000000001038]:bgeu t2, fp, 44
[0x8000000000103c]:ld fp, 472(s1)
[0x80000000001040]:ld a1, 480(s1)
[0x80000000001044]:add a1, a1, fp
[0x80000000001048]:bgeu t2, a1, 8
[0x8000000000104c]:bgeu t2, fp, 24
[0x80000000001064]:sub fp, t2, fp
[0x80000000001068]:sd fp, 16(t1)
[0x8000000000106c]:andi a1, t2, 4092
[0x80000000001070]:addi a1, a1, 8
[0x80000000001074]:csrrw zero, mepc, a1
[0x80000000001078]:csrrs t2, mtval, zero
[0x8000000000107c]:andi a0, a0, 15
[0x80000000001080]:lui fp, 0
[0x80000000001084]:addi fp, fp, 0
[0x80000000001088]:slli fp, fp, 11
[0x8000000000108c]:addi fp, fp, 0
[0x80000000001090]:slli fp, fp, 11
[0x80000000001094]:addi fp, fp, 44
[0x80000000001098]:slli fp, fp, 10
[0x8000000000109c]:addi fp, fp, 251
[0x800000000010a0]:srl fp, fp, a0
[0x800000000010a4]:slli fp, fp, 63
[0x800000000010a8]:bge fp, zero, 88
[0x800000000010ac]:ld fp, 520(s1)
[0x800000000010b0]:ld a1, 528(s1)
[0x800000000010b4]:add a1, a1, fp
[0x800000000010b8]:bgeu t2, a1, 8
[0x800000000010bc]:bgeu t2, fp, 64
[0x800000000010fc]:sub fp, t2, fp
[0x80000000001100]:sd fp, 24(t1)
[0x80000000001104]:ld s1, 536(sp)
[0x80000000001108]:ld t2, 504(sp)
[0x8000000000110c]:ld t1, 512(sp)
[0x80000000001110]:add t1, t1, t2
[0x80000000001114]:bltu t1, s1, 7036
[0x80000000001118]:addi t2, zero, 512
[0x8000000000111c]:jal zero, 64
[0x8000000000115c]:auipc fp, 0
[0x80000000001160]:addi fp, fp, 60
[0x80000000001164]:add fp, fp, t2
[0x80000000001168]:slli t2, a0, 3
[0x8000000000116c]:add fp, fp, t2
[0x80000000001170]:andi fp, fp, 4088
[0x80000000001174]:ld fp, 0(fp)
[0x80000000001178]:beq fp, zero, 7084
[0x8000000000117c]:slli t2, fp, 63
[0x80000000001180]:bge t2, zero, 16
[0x80000000001184]:srli fp, fp, 1
[0x80000000001188]:beq a0, fp, 8088
[0x80000000001120]:ld t1, 608(sp)
[0x80000000001124]:ld t2, 616(sp)
[0x80000000001128]:ld fp, 624(sp)
[0x8000000000112c]:ld s1, 632(sp)
[0x80000000001130]:ld a0, 640(sp)
[0x80000000001134]:ld a1, 648(sp)
[0x80000000001138]:ld sp, 656(sp)
[0x8000000000113c]:mret
[0x900000c4c]:lui a4, 0
[0x900000c50]:addi a4, a4, 0
[0x900000c54]:slli a4, a4, 11
[0x900000c58]:addi a4, a4, 0
[0x900000c5c]:slli a4, a4, 11
[0x900000c60]:addi a4, a4, 47
[0x900000c64]:slli a4, a4, 10
[0x900000c68]:addi a4, a4, 751
[0x900000c6c]:sd a4, 24(s11)
[0x900000c70]:addi zero, zero, 0
[0x900000c74]:addi sp, zero, 0
[0x900000c78]:ecall
[0x80000000000d80]:jal zero, 256
[0x80000000000e80]:csrrw sp, mscratch, sp
[0x80000000000e84]:sd a1, 648(sp)
[0x80000000000e88]:jal a1, 184
[0x80000000000f40]:sd a0, 640(sp)
[0x80000000000f44]:csrrw a0, mscratch, sp
[0x80000000000f48]:sd a0, 656(sp)
[0x80000000000f4c]:ld a0, 560(sp)
[0x80000000000f50]:jalr zero, a0, 0
[0x80000000000f54]:sd s1, 632(sp)
[0x80000000000f58]:sd fp, 624(sp)
[0x80000000000f5c]:sd t2, 616(sp)
[0x80000000000f60]:sd t1, 608(sp)
[0x80000000000f64]:csrrs a0, mcause, zero
[0x80000000000f68]:addi s1, a0, 4088
[0x80000000000f6c]:andi s1, s1, 4092
[0x80000000000f70]:bne s1, zero, 12
[0x80000000000f74]:ld t2, 656(sp)
[0x80000000000f78]:beq t2, zero, 1652
[0x800000000015ec]:addi s1, a0, 4085
[0x800000000015f0]:beq s1, zero, 32
[0x800000000015f4]:csrrs t2, mstatus, zero
[0x800000000015f8]:slli t2, t2, 24
[0x800000000015fc]:ld a1, 1136(sp)
[0x80000000001600]:bge t2, zero, 8
[0x80000000001608]:ld s1, 472(sp)
[0x8000000000160c]:sub s1, s1, a1
[0x80000000001610]:csrrs t2, mepc, zero
[0x80000000001614]:add t2, t2, s1
[0x80000000001618]:ld t1, 608(sp)
[0x8000000000161c]:ld fp, 624(sp)
[0x80000000001620]:ld s1, 632(sp)
[0x80000000001624]:ld a0, 640(sp)
[0x80000000001628]:ld a1, 648(sp)
[0x8000000000162c]:ld sp, 656(sp)
[0x80000000001630]:jalr zero, t2, 4
[0x80000000000c7c]:addi a3, a3, 8
[0x80000000000c80]:addi a4, zero, 291
[0x80000000000c84]:sd a4, 32(a3)
[0x80000000000c88]:addi sp, zero, 0
[0x80000000000c8c]:ecall
[0x80000000000d80]:jal zero, 256
[0x80000000000e80]:csrrw sp, mscratch, sp
[0x80000000000e84]:sd a1, 648(sp)
[0x80000000000e88]:jal a1, 184
[0x80000000000f40]:sd a0, 640(sp)
[0x80000000000f44]:csrrw a0, mscratch, sp
[0x80000000000f48]:sd a0, 656(sp)
[0x80000000000f4c]:ld a0, 560(sp)
[0x80000000000f50]:jalr zero, a0, 0
[0x80000000000f54]:sd s1, 632(sp)
[0x80000000000f58]:sd fp, 624(sp)
[0x80000000000f5c]:sd t2, 616(sp)
[0x80000000000f60]:sd t1, 608(sp)
[0x80000000000f64]:csrrs a0, mcause, zero
[0x80000000000f68]:addi s1, a0, 4088
[0x80000000000f6c]:andi s1, s1, 4092
[0x80000000000f70]:bne s1, zero, 12
[0x80000000000f74]:ld t2, 656(sp)
[0x80000000000f78]:beq t2, zero, 1652
[0x800000000015ec]:addi s1, a0, 4085
[0x800000000015f0]:beq s1, zero, 32
[0x80000000001610]:csrrs t2, mepc, zero
[0x80000000001614]:add t2, t2, s1
[0x80000000001618]:ld t1, 608(sp)
[0x8000000000161c]:ld fp, 624(sp)
[0x80000000001620]:ld s1, 632(sp)
[0x80000000001624]:ld a0, 640(sp)
[0x80000000001628]:ld a1, 648(sp)
[0x8000000000162c]:ld sp, 656(sp)
[0x80000000001630]:jalr zero, t2, 4
[0x80000000000c90]:csrrs t1, mscratch, zero
[0x80000000000c94]:addi t1, t1, 664
[0x80000000000c98]:ld t2, 568(t1)
[0x80000000000c9c]:ld t2, 544(t1)
[0x80000000000ca0]:csrrw zero, satp, t2

[0x900000c3c]:ld t0, 0(t0)
[0x80000000000d80]:jal zero, 256
[0x80000000000e80]:csrrw sp, mscratch, sp
[0x80000000000e84]:sd a1, 648(sp)
[0x80000000000e88]:jal a1, 184
[0x80000000000f40]:sd a0, 640(sp)
[0x80000000000f44]:csrrw a0, mscratch, sp
[0x80000000000f48]:sd a0, 656(sp)
[0x80000000000f4c]:ld a0, 560(sp)
[0x80000000000f50]:jalr zero, a0, 0
[0x80000000000f54]:sd s1, 632(sp)
[0x80000000000f58]:sd fp, 624(sp)
[0x80000000000f5c]:sd t2, 616(sp)
[0x80000000000f60]:sd t1, 608(sp)
[0x80000000000f64]:csrrs a0, mcause, zero
[0x80000000000f68]:addi s1, a0, 4088
[0x80000000000f6c]:andi s1, s1, 4092
[0x80000000000f70]:bne s1, zero, 12
[0x80000000000f7c]:addi t2, zero, 32
[0x80000000000f80]:bge a0, zero, 68
[0x80000000000fc4]:csrrs t1, misa, zero
[0x80000000000fc8]:slli t1, t1, 56
[0x80000000000fcc]:bge t1, zero, 8
[0x80000000000fd4]:ld t1, 536(sp)
[0x80000000000fd8]:add s1, t1, t2
[0x80000000000fdc]:sd s1, 536(sp)
[0x80000000000fe0]:ld fp, 576(sp)
[0x80000000000fe4]:sub a1, a1, fp
[0x80000000000fe8]:slli a1, a1, 4
[0x80000000000fec]:or a1, a1, t2
[0x80000000000ff0]:addi a1, a1, 3
[0x80000000000ff4]:sd a1, 0(t1)
[0x80000000000ff8]:sd a0, 8(t1)
[0x80000000000ffc]:blt a0, zero, 324
[0x80000000001000]:addi s1, sp, 0
[0x80000000001004]:csrrs a1, mstatus, zero
[0x80000000001008]:slli fp, a1, 51
[0x8000000000100c]:blt fp, zero, 24
[0x80000000001010]:addi s1, s1, 664
[0x80000000001014]:srli a1, a1, 32
[0x80000000001018]:slli a1, a1, 24
[0x8000000000101c]:bge a1, zero, 8
[0x80000000001024]:csrrs t2, mepc, zero
[0x80000000001028]:ld fp, 520(s1)
[0x8000000000102c]:ld a1, 528(s1)
[0x80000000001030]:add a1, a1, fp
[0x80000000001034]:bgeu t2, a1, 8
[0x80000000001038]:bgeu t2, fp, 44
[0x8000000000103c]:ld fp, 472(s1)
[0x80000000001040]:ld a1, 480(s1)
[0x80000000001044]:add a1, a1, fp
[0x80000000001048]:bgeu t2, a1, 8
[0x8000000000104c]:bgeu t2, fp, 24
[0x80000000001064]:sub fp, t2, fp
[0x80000000001068]:sd fp, 16(t1)
[0x8000000000106c]:andi a1, t2, 4092
[0x80000000001070]:addi a1, a1, 8
[0x80000000001074]:csrrw zero, mepc, a1
[0x80000000001078]:csrrs t2, mtval, zero
[0x8000000000107c]:andi a0, a0, 15
[0x80000000001080]:lui fp, 0
[0x80000000001084]:addi fp, fp, 0
[0x80000000001088]:slli fp, fp, 11
[0x8000000000108c]:addi fp, fp, 0
[0x80000000001090]:slli fp, fp, 11
[0x80000000001094]:addi fp, fp, 44
[0x80000000001098]:slli fp, fp, 10
[0x8000000000109c]:addi fp, fp, 251
[0x800000000010a0]:srl fp, fp, a0
[0x800000000010a4]:slli fp, fp, 63
[0x800000000010a8]:bge fp, zero, 88
[0x800000000010ac]:ld fp, 520(s1)
[0x800000000010b0]:ld a1, 528(s1)
[0x800000000010b4]:add a1, a1, fp
[0x800000000010b8]:bgeu t2, a1, 8
[0x800000000010bc]:bgeu t2, fp, 64
[0x800000000010fc]:sub fp, t2, fp
[0x80000000001100]:sd fp, 24(t1)
[0x80000000001104]:ld s1, 536(sp)
[0x80000000001108]:ld t2, 504(sp)
[0x8000000000110c]:ld t1, 512(sp)
[0x80000000001110]:add t1, t1, t2
[0x80000000001114]:bltu t1, s1, 7036
[0x80000000001118]:addi t2, zero, 512
[0x8000000000111c]:jal zero, 64
[0x8000000000115c]:auipc fp, 0
[0x80000000001160]:addi fp, fp, 60
[0x80000000001164]:add fp, fp, t2
[0x80000000001168]:slli t2, a0, 3
[0x8000000000116c]:add fp, fp, t2
[0x80000000001170]:andi fp, fp, 4088
[0x80000000001174]:ld fp, 0(fp)
[0x80000000001178]:beq fp, zero, 7084
[0x8000000000117c]:slli t2, fp, 63
[0x80000000001180]:bge t2, zero, 16
[0x80000000001184]:srli fp, fp, 1
[0x80000000001188]:beq a0, fp, 8088
[0x80000000001120]:ld t1, 608(sp)
[0x80000000001124]:ld t2, 616(sp)
[0x80000000001128]:ld fp, 624(sp)
[0x8000000000112c]:ld s1, 632(sp)
[0x80000000001130]:ld a0, 640(sp)
[0x80000000001134]:ld a1, 648(sp)
[0x80000000001138]:ld sp, 656(sp)
[0x8000000000113c]:mret
[0x900000c44]:sd sp, 0(t0)
[0x80000000000d80]:jal zero, 256
[0x80000000000e80]:csrrw sp, mscratch, sp
[0x80000000000e84]:sd a1, 648(sp)
[0x80000000000e88]:jal a1, 184
[0x80000000000f40]:sd a0, 640(sp)
[0x80000000000f44]:csrrw a0, mscratch, sp
[0x80000000000f48]:sd a0, 656(sp)
[0x80000000000f4c]:ld a0, 560(sp)
[0x80000000000f50]:jalr zero, a0, 0
[0x80000000000f54]:sd s1, 632(sp)
[0x80000000000f58]:sd fp, 624(sp)
[0x80000000000f5c]:sd t2, 616(sp)
[0x80000000000f60]:sd t1, 608(sp)
[0x80000000000f64]:csrrs a0, mcause, zero
[0x80000000000f68]:addi s1, a0, 4088
[0x80000000000f6c]:andi s1, s1, 4092
[0x80000000000f70]:bne s1, zero, 12
[0x80000000000f7c]:addi t2, zero, 32
[0x80000000000f80]:bge a0, zero, 68
[0x80000000000fc4]:csrrs t1, misa, zero
[0x80000000000fc8]:slli t1, t1, 56
[0x80000000000fcc]:bge t1, zero, 8
[0x80000000000fd4]:ld t1, 536(sp)
[0x80000000000fd8]:add s1, t1, t2
[0x80000000000fdc]:sd s1, 536(sp)
[0x80000000000fe0]:ld fp, 576(sp)
[0x80000000000fe4]:sub a1, a1, fp
[0x80000000000fe8]:slli a1, a1, 4
[0x80000000000fec]:or a1, a1, t2
[0x80000000000ff0]:addi a1, a1, 3
[0x80000000000ff4]:sd a1, 0(t1)
[0x80000000000ff8]:sd a0, 8(t1)
[0x80000000000ffc]:blt a0, zero, 324
[0x80000000001000]:addi s1, sp, 0
[0x80000000001004]:csrrs a1, mstatus, zero
[0x80000000001008]:slli fp, a1, 51
[0x8000000000100c]:blt fp, zero, 24
[0x80000000001010]:addi s1, s1, 664
[0x80000000001014]:srli a1, a1, 32
[0x80000000001018]:slli a1, a1, 24
[0x8000000000101c]:bge a1, zero, 8
[0x80000000001024]:csrrs t2, mepc, zero
[0x80000000001028]:ld fp, 520(s1)
[0x8000000000102c]:ld a1, 528(s1)
[0x80000000001030]:add a1, a1, fp
[0x80000000001034]:bgeu t2, a1, 8
[0x80000000001038]:bgeu t2, fp, 44
[0x8000000000103c]:ld fp, 472(s1)
[0x80000000001040]:ld a1, 480(s1)
[0x80000000001044]:add a1, a1, fp
[0x80000000001048]:bgeu t2, a1, 8
[0x8000000000104c]:bgeu t2, fp, 24
[0x80000000001064]:sub fp, t2, fp
[0x80000000001068]:sd fp, 16(t1)
[0x8000000000106c]:andi a1, t2, 4092
[0x80000000001070]:addi a1, a1, 8
[0x80000000001074]:csrrw zero, mepc, a1
[0x80000000001078]:csrrs t2, mtval, zero
[0x8000000000107c]:andi a0, a0, 15
[0x80000000001080]:lui fp, 0
[0x80000000001084]:addi fp, fp, 0
[0x80000000001088]:slli fp, fp, 11
[0x8000000000108c]:addi fp, fp, 0
[0x80000000001090]:slli fp, fp, 11
[0x80000000001094]:addi fp, fp, 44
[0x80000000001098]:slli fp, fp, 10
[0x8000000000109c]:addi fp, fp, 251
[0x800000000010a0]:srl fp, fp, a0
[0x800000000010a4]:slli fp, fp, 63
[0x800000000010a8]:bge fp, zero, 88
[0x800000000010ac]:ld fp, 520(s1)
[0x800000000010b0]:ld a1, 528(s1)
[0x800000000010b4]:add a1, a1, fp
[0x800000000010b8]:bgeu t2, a1, 8
[0x800000000010bc]:bgeu t2, fp, 64
[0x800000000010fc]:sub fp, t2, fp
[0x80000000001100]:sd fp, 24(t1)
[0x80000000001104]:ld s1, 536(sp)
[0x80000000001108]:ld t2, 504(sp)
[0x8000000000110c]:ld t1, 512(sp)
[0x80000000001110]:add t1, t1, t2
[0x80000000001114]:bltu t1, s1, 7036
[0x80000000001118]:addi t2, zero, 512
[0x8000000000111c]:jal zero, 64
[0x8000000000115c]:auipc fp, 0
[0x80000000001160]:addi fp, fp, 60
[0x80000000001164]:add fp, fp, t2
[0x80000000001168]:slli t2, a0, 3
[0x8000000000116c]:add fp, fp, t2
[0x80000000001170]:andi fp, fp, 4088
[0x80000000001174]:ld fp, 0(fp)
[0x80000000001178]:beq fp, zero, 7084
[0x8000000000117c]:slli t2, fp, 63
[0x80000000001180]:bge t2, zero, 16
[0x80000000001184]:srli fp, fp, 1
[0x80000000001188]:beq a0, fp, 8088
[0x80000000001120]:ld t1, 608(sp)
[0x80000000001124]:ld t2, 616(sp)
[0x80000000001128]:ld fp, 624(sp)
[0x8000000000112c]:ld s1, 632(sp)
[0x80000000001130]:ld a0, 640(sp)
[0x80000000001134]:ld a1, 648(sp)
[0x80000000001138]:ld sp, 656(sp)
[0x8000000000113c]:mret
[0x900000c4c]:lui a4, 0
[0x900000c50]:addi a4, a4, 0
[0x900000c54]:slli a4, a4, 11
[0x900000c58]:addi a4, a4, 0
[0x900000c5c]:slli a4, a4, 11
[0x900000c60]:addi a4, a4, 47
[0x900000c64]:slli a4, a4, 10
[0x900000c68]:addi a4, a4, 751
[0x900000c6c]:sd a4, 24(s11)
[0x900000c70]:addi zero, zero, 0
[0x900000c74]:addi sp, zero, 0
[0x900000c78]:ecall
[0x80000000000d80]:jal zero, 256
[0x80000000000e80]:csrrw sp, mscratch, sp
[0x80000000000e84]:sd a1, 648(sp)
[0x80000000000e88]:jal a1, 184
[0x80000000000f40]:sd a0, 640(sp)
[0x80000000000f44]:csrrw a0, mscratch, sp
[0x80000000000f48]:sd a0, 656(sp)
[0x80000000000f4c]:ld a0, 560(sp)
[0x80000000000f50]:jalr zero, a0, 0
[0x80000000000f54]:sd s1, 632(sp)
[0x80000000000f58]:sd fp, 624(sp)
[0x80000000000f5c]:sd t2, 616(sp)
[0x80000000000f60]:sd t1, 608(sp)
[0x80000000000f64]:csrrs a0, mcause, zero
[0x80000000000f68]:addi s1, a0, 4088
[0x80000000000f6c]:andi s1, s1, 4092
[0x80000000000f70]:bne s1, zero, 12
[0x80000000000f74]:ld t2, 656(sp)
[0x80000000000f78]:beq t2, zero, 1652
[0x800000000015ec]:addi s1, a0, 4085
[0x800000000015f0]:beq s1, zero, 32
[0x800000000015f4]:csrrs t2, mstatus, zero
[0x800000000015f8]:slli t2, t2, 24
[0x800000000015fc]:ld a1, 1136(sp)
[0x80000000001600]:bge t2, zero, 8
[0x80000000001608]:ld s1, 472(sp)
[0x8000000000160c]:sub s1, s1, a1
[0x80000000001610]:csrrs t2, mepc, zero
[0x80000000001614]:add t2, t2, s1
[0x80000000001618]:ld t1, 608(sp)
[0x8000000000161c]:ld fp, 624(sp)
[0x80000000001620]:ld s1, 632(sp)
[0x80000000001624]:ld a0, 640(sp)
[0x80000000001628]:ld a1, 648(sp)
[0x8000000000162c]:ld sp, 656(sp)
[0x80000000001630]:jalr zero, t2, 4
[0x80000000000c7c]:addi a3, a3, 8
[0x80000000000c80]:addi a4, zero, 291
[0x80000000000c84]:sd a4, 32(a3)
[0x80000000000c88]:addi sp, zero, 0
[0x80000000000c8c]:ecall
[0x80000000000d80]:jal zero, 256
[0x80000000000e80]:csrrw sp, mscratch, sp
[0x80000000000e84]:sd a1, 648(sp)
[0x80000000000e88]:jal a1, 184
[0x80000000000f40]:sd a0, 640(sp)
[0x80000000000f44]:csrrw a0, mscratch, sp
[0x80000000000f48]:sd a0, 656(sp)
[0x80000000000f4c]:ld a0, 560(sp)
[0x80000000000f50]:jalr zero, a0, 0
[0x80000000000f54]:sd s1, 632(sp)
[0x80000000000f58]:sd fp, 624(sp)
[0x80000000000f5c]:sd t2, 616(sp)
[0x80000000000f60]:sd t1, 608(sp)
[0x80000000000f64]:csrrs a0, mcause, zero
[0x80000000000f68]:addi s1, a0, 4088
[0x80000000000f6c]:andi s1, s1, 4092
[0x80000000000f70]:bne s1, zero, 12
[0x80000000000f74]:ld t2, 656(sp)
[0x80000000000f78]:beq t2, zero, 1652
[0x800000000015ec]:addi s1, a0, 4085
[0x800000000015f0]:beq s1, zero, 32
[0x80000000001610]:csrrs t2, mepc, zero
[0x80000000001614]:add t2, t2, s1
[0x80000000001618]:ld t1, 608(sp)
[0x8000000000161c]:ld fp, 624(sp)
[0x80000000001620]:ld s1, 632(sp)
[0x80000000001624]:ld a0, 640(sp)
[0x80000000001628]:ld a1, 648(sp)
[0x8000000000162c]:ld sp, 656(sp)
[0x80000000001630]:jalr zero, t2, 4
[0x80000000000c90]:csrrs t1, mscratch, zero
[0x80000000000c94]:addi t1, t1, 664
[0x80000000000c98]:ld t2, 568(t1)
[0x80000000000c9c]:ld t2, 544(t1)
[0x80000000000ca0]:csrrw zero, satp, t2
[0x80000000000ca4]:ld a0, 592(t1)
[0x80000000000ca8]:csrrw zero, sscratch, a0
[0x80000000000cac]:ld s1, 584(t1)
[0x80000000000cb0]:csrrw t2, stvec, s1
[0x80000000000cb4]:andi s1, s1, 4092
[0x80000000000cb8]:andi t2, t2, 4092
[0x80000000000cbc]:bne s1, t2, 32
[0x80000000000cdc]:csrrs t1, mscratch, zero
[0x80000000000ce0]:ld t2, 568(t1)
[0x80000000000ce4]:csrrw zero, medeleg, t2
[0x80000000000ce8]:ld a0, 592(t1)
[0x80000000000cec]:csrrw zero, mscratch, a0
[0x80000000000cf0]:ld s1, 584(t1)
[0x80000000000cf4]:csrrw t2, mtvec, s1
[0x80000000000cf8]:andi s1, s1, 4092
[0x80000000000cfc]:andi t2, t2, 4092
[0x80000000000d00]:bne s1, t2, 32
[0x80000000000d20]:jal zero, 4444
[0x80000000001e7c]:addi ra, zero, 1
[0x80000000001e80]:auipc t5, 0
[0x80000000001e84]:sw ra, 384(t5)
[0x80000000001e88]:jal zero, 2097144
[0x80000000001e80]:auipc t5, 0
[0x80000000001e84]:sw ra, 384(t5)
[0x80000000001e88]:jal zero, 2097144
[0x80000000001e80]:auipc t5, 0
[0x80000000001e84]:sw ra, 384(t5)



```

## Details of STAT4:

```

```

## Details of STAT5:



## Details of STAT1:

- The first column indicates the signature address(es) and the data at that location in hexadecimal in the following format:
  ```
  [Address1]
  Data1

  [Address2]
  Data2

  ...
  ```

- The second column captures all the coverpoints which have been captured by that particular signature location

- The third column captures all the insrtuctions since the time a coverpoint was
  hit to the point when a store to the signature was performed. Each line has
  the following format:
  ```
  [PC of instruction] : mnemonic
  ```
- The order in the table is based on the order of signatures occuring in the
  test. These need not necessarily be in increasing or decreasing order of the
  address in the signature region.

|s.no|signature|coverpoints|code|
|----|---------|-----------|----|
