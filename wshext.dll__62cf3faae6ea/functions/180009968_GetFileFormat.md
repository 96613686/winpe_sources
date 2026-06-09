# GetFileFormat

- ea: `0x180009968`
- end: `0x180009a86`
- name: `GetFileFormat`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009078`

## callees

- `0x180009968`
- `0x18000e010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180009a6f`
- `KERNEL32!SetLastError` at `0x180009a6f`
- `ole32!CoInitialize` at `0x18000998e`
- `ole32!CoInitialize` at `0x18000998e`
- `ole32!CoUninitialize` at `0x180009a62`
- `ole32!CoUninitialize` at `0x180009a62`
- `ole32!CoCreateInstance` at `0x1800099bc`
- `ole32!CoCreateInstance` at `0x1800099bc`

## pseudocode

```c
__int64 __fastcall GetFileFormat(_BYTE *a1, unsigned int a2, int *a3, _DWORD *a4)
{
  unsigned int v5; // esi
  DWORD v9; // r15d
  int v10; // edi
  bool v11; // zf
  int v12; // eax
  LPVOID ppv; // [rsp+30h] [rbp-48h] BYREF

  v5 = 0;
  ppv = 0;
  v9 = 0;
  if ( CoInitialize(0) >= 0 )
  {
    v10 = 1;
    if ( CoCreateInstance(&CLSID_ScriptletConstructor, 0, 1u, &IID_IConvertXMLBytesToUnicode, &ppv) < 0 )
    {
      v9 = 8;
      goto LABEL_22;
    }
    (*(void (__fastcall **)(LPVOID, _BYTE *, _QWORD, _QWORD, _DWORD *))(*(_QWORD *)ppv + 24LL))(ppv, a1, a2, 0, a4);
    if ( *a4 == 1200 )
    {
      if ( a2 < 2 || *a1 != 0xFF )
        goto LABEL_19;
      v11 = a1[1] == 0xFE;
    }
    else if ( *a4 == 1201 )
    {
      if ( a2 < 2 || *a1 != 0xFE )
        goto LABEL_19;
      v11 = a1[1] == 0xFF;
    }
    else
    {
      if ( *a4 != 65001 || a2 < 3 || *a1 != 0xEF || a1[1] != 0xBB )
        goto LABEL_19;
      v11 = a1[2] == 0xBF;
    }
    if ( v11 )
    {
      v12 = 1;
LABEL_20:
      *a3 = v12;
      v5 = 1;
      goto LABEL_22;
    }
LABEL_19:
    v12 = 0;
    goto LABEL_20;
  }
  v10 = 0;
LABEL_22:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v10 )
    CoUninitialize();
  if ( !v5 )
    SetLastError(v9);
  return v5;
}

```

## disassembly

```asm
0x180009968  push    rbx
0x18000996a  push    rbp
0x18000996b  push    rsi
0x18000996c  push    rdi
0x18000996d  push    r12
0x18000996f  push    r14
0x180009971  push    r15
0x180009973  sub     rsp, 40h
0x180009977  mov     rbx, rcx
0x18000997a  xor     esi, esi
0x18000997c  xor     ecx, ecx; pvReserved
0x18000997e  mov     [rsp+78h+var_48], rsi
0x180009983  mov     r14, r9
0x180009986  mov     r12, r8
0x180009989  mov     ebp, edx
0x18000998b  xor     r15d, r15d
0x18000998e  call    cs:__imp_CoInitialize
0x180009994  test    eax, eax
0x180009996  js      loc_180009A46
0x18000999c  lea     rax, [rsp+78h+var_48]
0x1800099a1  xor     edx, edx; pUnkOuter
0x1800099a3  lea     edi, [rsi+1]
0x1800099a6  mov     [rsp+78h+ppv], rax; ppv
0x1800099ab  mov     r8d, edi; dwClsContext
0x1800099ae  lea     r9, IID_IConvertXMLBytesToUnicode; riid
0x1800099b5  lea     rcx, CLSID_ScriptletConstructor; rclsid
0x1800099bc  call    cs:__imp_CoCreateInstance
0x1800099c2  test    eax, eax
0x1800099c4  jns     short loc_1800099CC
0x1800099c6  lea     r15d, [rsi+8]
0x1800099ca  jmp     short loc_180009A48
0x1800099cc  mov     rcx, [rsp+78h+var_48]
0x1800099d1  xor     r9d, r9d
0x1800099d4  mov     r8d, ebp
0x1800099d7  mov     [rsp+78h+ppv], r14
0x1800099dc  mov     rdx, rbx
0x1800099df  mov     rax, [rcx]
0x1800099e2  mov     rax, [rax+18h]
0x1800099e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099eb  mov     ecx, [r14]
0x1800099ee  sub     ecx, 4B0h
0x1800099f4  jz      short loc_180009A28
0x1800099f6  sub     ecx, edi
0x1800099f8  jz      short loc_180009A18
0x1800099fa  cmp     ecx, 0F938h
0x180009a00  jnz     short loc_180009A3C
0x180009a02  cmp     ebp, 3
0x180009a05  jb      short loc_180009A3C
0x180009a07  cmp     byte ptr [rbx], 0EFh
0x180009a0a  jnz     short loc_180009A3C
0x180009a0c  cmp     byte ptr [rbx+1], 0BBh
0x180009a10  jnz     short loc_180009A3C
0x180009a12  cmp     byte ptr [rbx+2], 0BFh
0x180009a16  jmp     short loc_180009A36
0x180009a18  cmp     ebp, 2
0x180009a1b  jb      short loc_180009A3C
0x180009a1d  cmp     byte ptr [rbx], 0FEh
0x180009a20  jnz     short loc_180009A3C
0x180009a22  cmp     byte ptr [rbx+1], 0FFh
0x180009a26  jmp     short loc_180009A36
0x180009a28  cmp     ebp, 2
0x180009a2b  jb      short loc_180009A3C
0x180009a2d  cmp     byte ptr [rbx], 0FFh
0x180009a30  jnz     short loc_180009A3C
0x180009a32  cmp     byte ptr [rbx+1], 0FEh
0x180009a36  jnz     short loc_180009A3C
0x180009a38  mov     eax, edi
0x180009a3a  jmp     short loc_180009A3E
0x180009a3c  xor     eax, eax
0x180009a3e  mov     [r12], eax
0x180009a42  mov     esi, edi
0x180009a44  jmp     short loc_180009A48
0x180009a46  xor     edi, edi
0x180009a48  mov     rcx, [rsp+78h+var_48]
0x180009a4d  test    rcx, rcx
0x180009a50  jz      short loc_180009A5E
0x180009a52  mov     rax, [rcx]
0x180009a55  mov     rax, [rax+10h]
0x180009a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a5e  test    edi, edi
0x180009a60  jz      short loc_180009A68
0x180009a62  call    cs:__imp_CoUninitialize
0x180009a68  test    esi, esi
0x180009a6a  jnz     short loc_180009A75
0x180009a6c  mov     ecx, r15d; dwErrCode
0x180009a6f  call    cs:__imp_SetLastError
0x180009a75  mov     eax, esi
0x180009a77  add     rsp, 40h
0x180009a7b  pop     r15
0x180009a7d  pop     r14
0x180009a7f  pop     r12
0x180009a81  pop     rdi
0x180009a82  pop     rsi
0x180009a83  pop     rbp
0x180009a84  pop     rbx
0x180009a85  retn
```
