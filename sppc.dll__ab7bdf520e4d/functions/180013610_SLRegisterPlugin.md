# SLRegisterPlugin

- ea: `0x180013610`
- end: `0x180013720`
- name: `SLRegisterPlugin`
- size: `272`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x180001760`
- `0x180001a90`
- `0x180003030`
- `0x1800044dc`
- `0x180005208`
- `0x180006844`
- `0x18000a8d0`
- `0x18000f144`
- `0x180013610`

## pseudocode

```c
__int64 __fastcall SLRegisterPlugin(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rcx
  int v8; // eax
  _QWORD v10[2]; // [rsp+30h] [rbp-28h] BYREF
  __int128 v11; // [rsp+40h] [rbp-18h] BYREF

  v11 = 0;
  v10[0] = (char *)&v11 + 8;
  sub_180001A90(qword_180018818, qword_18001EA48);
  v10[1] = &v11;
  if ( !a1 )
  {
    v6 = -2147024809;
    sub_180001760(qword_180019428, &dword_18001EAB4);
LABEL_3:
    v7 = 2147942487LL;
LABEL_12:
    sub_180006844(v7);
    goto LABEL_13;
  }
  if ( !a2 || !a3 )
  {
    v6 = -2147024809;
    goto LABEL_3;
  }
  v8 = sub_18000F144(v10, 1, a2);
  v6 = v8;
  if ( v8 < 0 || (v8 = sub_18000F144(v10, 2, a3), v6 = v8, v8 < 0) )
  {
    v7 = (unsigned int)v8;
    goto LABEL_12;
  }
  v6 = sub_1800044DC((unsigned int)v10, a1, 35, 0, 1);
  if ( (v6 & 0x80000000) != 0 )
  {
    sub_180003030(&dword_180019FF4, &dword_18001E8C4);
    v7 = v6;
    goto LABEL_12;
  }
LABEL_13:
  sub_18000A8D0(v6);
  sub_180005208(v10);
  return v6;
}

```

## disassembly

```asm
0x180013610  mov     rax, rsp
0x180013613  mov     [rax+8], rbx
0x180013617  mov     [rax+10h], rsi
0x18001361b  push    rdi
0x18001361c  sub     rsp, 50h
0x180013620  xorps   xmm0, xmm0
0x180013623  mov     rbx, rdx
0x180013626  mov     rsi, rcx
0x180013629  lea     rdx, qword_18001EA48
0x180013630  mov     rdi, r8
0x180013633  lea     rcx, qword_180018818
0x18001363a  movdqu  xmmword ptr [rax-18h], xmm0
0x18001363f  lea     rax, [rax-10h]
0x180013643  mov     [rsp+58h+var_28], rax
0x180013648  call    sub_180001A90
0x18001364d  lea     rax, [rsp+58h+var_18]
0x180013652  mov     [rsp+58h+var_20], rax
0x180013657  test    rsi, rsi
0x18001365a  jnz     short loc_18001367A
0x18001365c  mov     edi, 80070057h
0x180013661  lea     rdx, dword_18001EAB4
0x180013668  lea     rcx, qword_180019428
0x18001366f  mov     ebx, edi
0x180013671  call    sub_180001760
0x180013676  mov     ecx, edi
0x180013678  jmp     short loc_1800136F8
0x18001367a  test    rbx, rbx
0x18001367d  jnz     short loc_180013688
0x18001367f  mov     edi, 80070057h
0x180013684  mov     ebx, edi
0x180013686  jmp     short loc_180013676
0x180013688  test    rdi, rdi
0x18001368b  jz      short loc_18001367F
0x18001368d  mov     r8, rbx
0x180013690  lea     rcx, [rsp+58h+var_28]
0x180013695  mov     edx, 1
0x18001369a  call    sub_18000F144
0x18001369f  mov     ebx, eax
0x1800136a1  test    eax, eax
0x1800136a3  jns     short loc_1800136A9
0x1800136a5  mov     ecx, eax
0x1800136a7  jmp     short loc_1800136F8
0x1800136a9  mov     r8, rdi
0x1800136ac  lea     rcx, [rsp+58h+var_28]
0x1800136b1  mov     edx, 2
0x1800136b6  call    sub_18000F144
0x1800136bb  mov     ebx, eax
0x1800136bd  test    eax, eax
0x1800136bf  js      short loc_1800136A5
0x1800136c1  xor     r9d, r9d
0x1800136c4  mov     [rsp+58h+var_38], 1
0x1800136cc  mov     rdx, rsi
0x1800136cf  lea     rcx, [rsp+58h+var_28]
0x1800136d4  lea     r8d, [r9+23h]
0x1800136d8  call    sub_1800044DC
0x1800136dd  mov     ebx, eax
0x1800136df  test    eax, eax
0x1800136e1  jns     short loc_1800136FD
0x1800136e3  lea     rdx, dword_18001E8C4
0x1800136ea  lea     rcx, dword_180019FF4
0x1800136f1  call    sub_180003030
0x1800136f6  mov     ecx, ebx
0x1800136f8  call    sub_180006844
0x1800136fd  mov     ecx, ebx
0x1800136ff  call    sub_18000A8D0
0x180013704  lea     rcx, [rsp+58h+var_28]
0x180013709  call    sub_180005208
0x18001370e  mov     rsi, [rsp+58h+arg_8]
0x180013713  mov     eax, ebx
0x180013715  mov     rbx, [rsp+58h+arg_0]
0x18001371a  add     rsp, 50h
0x18001371e  pop     rdi
0x18001371f  retn
```
