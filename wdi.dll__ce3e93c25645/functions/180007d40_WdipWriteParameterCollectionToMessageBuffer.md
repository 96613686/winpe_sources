# WdipWriteParameterCollectionToMessageBuffer

- ea: `0x180007d40`
- end: `0x180007ed8`
- name: `WdipWriteParameterCollectionToMessageBuffer`
- size: `408`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003f40`
- `0x18000a420`
- `0x18000ab6c`

## callees

- `0x180002ba0`
- `0x180007d40`
- `0x18000ed58`

## string_xrefs

- `0x180007d79`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x180007ebb`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x180007d72`: `WdipWriteParameterCollectionToMessageBuffer`
- `0x180007eb4`: `WdipWriteParameterCollectionToMessageBuffer`

## pseudocode

```c
__int64 __fastcall WdipWriteParameterCollectionToMessageBuffer(__int64 a1, unsigned __int64 a2, unsigned int a3)
{
  unsigned int v6; // ebx
  int v7; // r8d
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // rdx
  int v11; // r8d
  int v12; // ebx
  int v13; // r14d
  __int64 i; // rsi
  __int64 v15; // r15
  int Args; // [rsp+20h] [rbp-38h]
  unsigned __int8 *v17; // [rsp+60h] [rbp+8h] BYREF

  if ( !a1 )
  {
    v6 = -2147024809;
    Args = 87;
    v7 = 621;
LABEL_3:
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (__int64)L"WdipWriteParameterCollectionToMessageBuffer",
      v7,
      (const wchar_t *)L"Error = %d",
      Args);
    return v6;
  }
  v9 = a2 + *(unsigned int *)(a2 + 124) + 40LL;
  if ( !v9 )
  {
    v6 = -2147024882;
    Args = 14;
    v7 = 623;
    goto LABEL_3;
  }
  if ( v9 < a2 || v9 - a2 > a3 || a2 + a3 - v9 < 4 )
  {
    v11 = 629;
    goto LABEL_19;
  }
  v10 = v9 + 4;
  if ( !v10 || v10 < a2 || v10 - a2 > a3 || a2 + a3 - v10 < 4 )
  {
    v11 = 636;
LABEL_19:
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (__int64)L"WdipWriteParameterCollectionToMessageBuffer",
      v11,
      (const wchar_t *)L"Error = %d",
      111);
    return 2147942934LL;
  }
  v12 = 0;
  v13 = 0;
  v17 = (unsigned __int8 *)(v10 + 4);
  for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 4); v13 += *(_DWORD *)(*(_QWORD *)(v15 + *(_QWORD *)(a1 + 8)) + 32LL) )
  {
    v15 = 8 * i;
    v12 = WdipWriteParameterToMessageBuffer(
            *(struct __WDIP_PARAMETER **)(8 * i + *(_QWORD *)(a1 + 8)),
            (struct _DPS_MESSAGE *)a2,
            a3,
            &v17);
    if ( v12 < 0 )
      break;
    i = (unsigned int)(i + 1);
  }
  v17 = (unsigned __int8 *)(a2 + *(unsigned int *)(a2 + 124) + 40LL);
  *(_DWORD *)v17 = i;
  *((_DWORD *)v17 + 1) = v13;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180007d40  push    rbx
0x180007d42  push    rbp
0x180007d43  push    rdi
0x180007d44  push    r12
0x180007d46  sub     rsp, 38h
0x180007d4a  mov     r12d, r8d
0x180007d4d  mov     rdi, rdx
0x180007d50  mov     rbp, rcx
0x180007d53  test    rcx, rcx
0x180007d56  jnz     short loc_180007D91
0x180007d58  mov     ebx, 80070057h
0x180007d5d  mov     dword ptr [rsp+58h+Args], 57h ; 'W'; Args
0x180007d65  mov     r8d, 26Dh; int
0x180007d6b  lea     r9, aErrorD_0; "Error = %d"
0x180007d72  lea     rdx, aWdipwriteparam_0; "WdipWriteParameterCollectionToMessageBu"...
0x180007d79  lea     rcx, aClientcoreBase_14; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180007d80  call    WdipTraceError
0x180007d85  mov     eax, ebx
0x180007d87  add     rsp, 38h
0x180007d8b  pop     r12
0x180007d8d  pop     rdi
0x180007d8e  pop     rbp
0x180007d8f  pop     rbx
0x180007d90  retn
0x180007d91  mov     edx, [rdx+7Ch]
0x180007d94  add     rdx, 28h ; '('
0x180007d98  add     rdx, rdi
0x180007d9b  jnz     short loc_180007DB2
0x180007d9d  mov     ebx, 8007000Eh
0x180007da2  mov     dword ptr [rsp+58h+Args], 0Eh
0x180007daa  mov     r8d, 26Fh
0x180007db0  jmp     short loc_180007D6B
0x180007db2  cmp     rdx, rdi
0x180007db5  jb      loc_180007E9F
0x180007dbb  mov     rax, rdx
0x180007dbe  mov     rcx, r12
0x180007dc1  sub     rax, rdi
0x180007dc4  cmp     rax, r12
0x180007dc7  ja      loc_180007E9F
0x180007dcd  mov     rax, rcx
0x180007dd0  sub     rax, rdx
0x180007dd3  add     rax, rdi
0x180007dd6  cmp     rax, 4
0x180007dda  jb      loc_180007E9F
0x180007de0  add     rdx, 4
0x180007de4  jz      short loc_180007DF6
0x180007de6  cmp     rdx, rdi
0x180007de9  jb      short loc_180007DF6
0x180007deb  mov     rax, rdx
0x180007dee  sub     rax, rdi
0x180007df1  cmp     rax, rcx
0x180007df4  jbe     short loc_180007E01
0x180007df6  mov     r8d, 27Ch
0x180007dfc  jmp     loc_180007EA5
0x180007e01  sub     rcx, rdx
0x180007e04  add     rcx, rdi
0x180007e07  cmp     rcx, 4
0x180007e0b  jb      short loc_180007DF6
0x180007e0d  mov     [rsp+58h+arg_8], rsi
0x180007e12  lea     rax, [rdx+4]
0x180007e16  mov     [rsp+58h+arg_10], r14
0x180007e1b  xor     ebx, ebx
0x180007e1d  xor     r14d, r14d
0x180007e20  mov     [rsp+58h+arg_0], rax
0x180007e25  xor     esi, esi
0x180007e27  cmp     [rbp+4], ebx
0x180007e2a  jbe     short loc_180007E6F
0x180007e2c  mov     [rsp+58h+var_28], r15
0x180007e31  mov     rcx, [rbp+8]
0x180007e35  lea     r15, ds:0[rsi*8]
0x180007e3d  lea     r9, [rsp+58h+arg_0]; unsigned __int8 **
0x180007e42  mov     r8d, r12d; unsigned int
0x180007e45  mov     rdx, rdi; struct _DPS_MESSAGE *
0x180007e48  mov     rcx, [r15+rcx]; struct __WDIP_PARAMETER *
0x180007e4c  call    ?WdipWriteParameterToMessageBuffer@@YAJPEAU__WDIP_PARAMETER@@PEAU_DPS_MESSAGE@@KPEAPEAE@Z; WdipWriteParameterToMessageBuffer(__WDIP_PARAMETER *,_DPS_MESSAGE *,ulong,uchar * *)
0x180007e51  mov     ebx, eax
0x180007e53  test    eax, eax
0x180007e55  js      short loc_180007E6A
0x180007e57  mov     rcx, [rbp+8]
0x180007e5b  inc     esi
0x180007e5d  mov     rdx, [r15+rcx]
0x180007e61  add     r14d, [rdx+20h]
0x180007e65  cmp     esi, [rbp+4]
0x180007e68  jb      short loc_180007E31
0x180007e6a  mov     r15, [rsp+58h+var_28]
0x180007e6f  mov     ecx, [rdi+7Ch]
0x180007e72  add     rcx, 28h ; '('
0x180007e76  add     rcx, rdi
0x180007e79  mov     [rsp+58h+arg_0], rcx
0x180007e7e  mov     [rcx], esi
0x180007e80  mov     rax, [rsp+58h+arg_0]
0x180007e85  mov     rsi, [rsp+58h+arg_8]
0x180007e8a  mov     [rax+4], r14d
0x180007e8e  mov     eax, ebx
0x180007e90  mov     r14, [rsp+58h+arg_10]
0x180007e95  add     rsp, 38h
0x180007e99  pop     r12
0x180007e9b  pop     rdi
0x180007e9c  pop     rbp
0x180007e9d  pop     rbx
0x180007e9e  retn
0x180007e9f  mov     r8d, 275h; int
0x180007ea5  lea     r9, aErrorD_0; "Error = %d"
0x180007eac  mov     dword ptr [rsp+58h+Args], 6Fh ; 'o'; Args
0x180007eb4  lea     rdx, aWdipwriteparam_0; "WdipWriteParameterCollectionToMessageBu"...
0x180007ebb  lea     rcx, aClientcoreBase_14; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180007ec2  call    WdipTraceError
0x180007ec7  mov     ebx, 80070216h
0x180007ecc  mov     eax, ebx
0x180007ece  add     rsp, 38h
0x180007ed2  pop     r12
0x180007ed4  pop     rdi
0x180007ed5  pop     rbp
0x180007ed6  pop     rbx
0x180007ed7  retn
```
