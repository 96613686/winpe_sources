# SLUninstallProofOfPurchase

- ea: `0x180013c20`
- end: `0x180013cff`
- name: `SLUninstallProofOfPurchase`
- size: `223`
- prototype: `HRESULT __stdcall(HSLC hSLC, const SLID *pPKeyId)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x180001430`
- `0x180002610`
- `0x180003410`
- `0x1800044dc`
- `0x180004f44`
- `0x180005208`
- `0x180006844`
- `0x18000a8d0`
- `0x180013c20`

## pseudocode

```c
HRESULT __stdcall SLUninstallProofOfPurchase(HSLC hSLC, const SLID *pPKeyId)
{
  __int64 v4; // rcx
  HRESULT v5; // ebx
  int v6; // eax
  __int64 v8[2]; // [rsp+30h] [rbp-28h] BYREF
  __int128 v9; // [rsp+40h] [rbp-18h] BYREF

  v9 = 0;
  v8[0] = (__int64)&v9 + 8;
  v8[1] = (__int64)&v9;
  sub_180002610(&dword_1800194CC, qword_18001EB28);
  if ( !hSLC || !pPKeyId )
  {
    v4 = 2147942487LL;
    v5 = -2147024809;
LABEL_3:
    sub_180006844(v4);
    goto LABEL_9;
  }
  v5 = sub_180004F44(v8, 1, pPKeyId);
  sub_180001430(byte_180019D78, byte_18001E598);
  if ( v5 < 0 )
  {
    v4 = (unsigned int)v5;
    goto LABEL_3;
  }
  v6 = sub_1800044DC(v8, (__int64)hSLC, 3u, 0, 1);
  v5 = v6;
  if ( v6 < 0 )
  {
    sub_180006844((unsigned int)v6);
    sub_180003410(byte_180018900, byte_18001EB18);
  }
LABEL_9:
  sub_18000A8D0((unsigned int)v5);
  sub_180005208(v8);
  return v5;
}

```

## disassembly

```asm
0x180013c20  mov     r11, rsp
0x180013c23  mov     [r11+8], rbx
0x180013c27  push    rdi
0x180013c28  sub     rsp, 50h
0x180013c2c  lea     rax, [r11-10h]
0x180013c30  xorps   xmm0, xmm0
0x180013c33  movdqu  [rsp+58h+var_18], xmm0
0x180013c39  mov     [r11-28h], rax
0x180013c3d  mov     rbx, rdx
0x180013c40  lea     rax, [r11-18h]
0x180013c44  mov     rdi, rcx
0x180013c47  lea     rdx, qword_18001EB28
0x180013c4e  mov     [r11-20h], rax
0x180013c52  lea     rcx, dword_1800194CC
0x180013c59  call    sub_180002610
0x180013c5e  test    rdi, rdi
0x180013c61  jnz     short loc_180013C71
0x180013c63  mov     ecx, 80070057h
0x180013c68  mov     ebx, ecx
0x180013c6a  call    sub_180006844
0x180013c6f  jmp     short loc_180013CE1
0x180013c71  test    rbx, rbx
0x180013c74  jz      short loc_180013C63
0x180013c76  mov     r8, rbx
0x180013c79  lea     rcx, [rsp+58h+var_28]
0x180013c7e  mov     edx, 1
0x180013c83  call    sub_180004F44
0x180013c88  lea     rdx, byte_18001E598
0x180013c8f  mov     ebx, eax
0x180013c91  lea     rcx, byte_180019D78
0x180013c98  call    sub_180001430
0x180013c9d  test    ebx, ebx
0x180013c9f  jns     short loc_180013CA5
0x180013ca1  mov     ecx, ebx
0x180013ca3  jmp     short loc_180013C6A
0x180013ca5  xor     r9d, r9d
0x180013ca8  mov     [rsp+58h+var_38], 1
0x180013cb0  mov     rdx, rdi
0x180013cb3  lea     rcx, [rsp+58h+var_28]
0x180013cb8  lea     r8d, [r9+3]
0x180013cbc  call    sub_1800044DC
0x180013cc1  mov     ebx, eax
0x180013cc3  test    eax, eax
0x180013cc5  jns     short loc_180013CE1
0x180013cc7  mov     ecx, eax
0x180013cc9  call    sub_180006844
0x180013cce  lea     rdx, byte_18001EB18
0x180013cd5  lea     rcx, byte_180018900
0x180013cdc  call    sub_180003410
0x180013ce1  mov     ecx, ebx
0x180013ce3  call    sub_18000A8D0
0x180013ce8  lea     rcx, [rsp+58h+var_28]
0x180013ced  call    sub_180005208
0x180013cf2  mov     eax, ebx
0x180013cf4  mov     rbx, [rsp+58h+arg_0]
0x180013cf9  add     rsp, 50h
0x180013cfd  pop     rdi
0x180013cfe  retn
```
