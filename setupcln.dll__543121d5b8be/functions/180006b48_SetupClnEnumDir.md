# SetupClnEnumDir

- ea: `0x180006b48`
- end: `0x180006f71`
- name: `SetupClnEnumDir`
- size: `1065`
- prototype: `__int64 __fastcall(__int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, installer_update`

## callers

- `0x180006868`

## callees

- `0x180002fe8`
- `0x180003a78`
- `0x180003ac4`
- `0x180003c98`
- `0x1800047ac`
- `0x180006b48`
- `0x18000827c`
- `0x180008aac`
- `0x180008ad0`
- `0x18000a780`
- `0x18000b348`
- `0x18000bb18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006bb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006bd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006bb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006bd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c38`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006c1d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006c1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006c09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006e53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ef9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006f1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006c09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006e53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ef9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006f1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006e61`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006f07`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006f29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006e61`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006f07`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006f29`
- `WDSCORE!CurrentIP` at `0x180006c40`
- `WDSCORE!CurrentIP` at `0x180006c40`
- `WDSCORE!WdsSetupLogMessageW` at `0x180006ca7`
- `WDSCORE!WdsSetupLogMessageW` at `0x180006ca7`

## string_xrefs

- `0x180006c4d`: `SetupClnEnumDir Failed to allocate buffer to handle hardlinks for [%s]`

## pseudocode

```c
__int64 __fastcall SetupClnEnumDir(__int64 a1, const wchar_t *a2)
{
  __int64 v4; // rbx
  signed int v5; // esi
  signed int LastError; // eax
  bool v7; // sf
  signed int v8; // eax
  HANDLE ProcessHeap; // rax
  LPVOID v10; // rax
  DWORD v11; // edi
  __int64 v12; // rbx
  struct tagLOG_PARTIAL_MSG *v13; // rax
  __int64 v14; // rdi
  __int64 v15; // rbx
  __int64 v16; // rdx
  LPCWSTR v17; // r10
  int v18; // eax
  __int64 v19; // rdi
  __int64 v20; // rbx
  __int64 v21; // r8
  void *v22; // rbx
  int v23; // eax
  HANDLE v24; // rax
  __int64 v25; // rdi
  __int64 v26; // rbx
  __int64 v27; // r8
  void *v28; // rbx
  HANDLE v29; // rax
  void *v30; // rbx
  HANDLE v31; // rax
  __int128 v33; // [rsp+60h] [rbp-59h] BYREF
  __int64 v34; // [rsp+70h] [rbp-49h]
  __int128 v35; // [rsp+78h] [rbp-41h] BYREF
  __int64 v36; // [rsp+88h] [rbp-31h]
  _QWORD v37[2]; // [rsp+90h] [rbp-29h] BYREF
  unsigned __int64 v38; // [rsp+A0h] [rbp-19h]
  _BYTE v39[24]; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v40; // [rsp+C0h] [rbp+7h]
  __int64 v41; // [rsp+C8h] [rbp+Fh]
  _BYTE v42[24]; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v43; // [rsp+E8h] [rbp+2Fh]
  __int64 v44; // [rsp+F0h] [rbp+37h]
  __int64 v45; // [rsp+128h] [rbp+6Fh] BYREF

  std::stack<unsigned short const *>::stack<unsigned short const *,std::deque<unsigned short const *>>(v39);
  std::stack<unsigned short const *>::stack<unsigned short const *,std::deque<unsigned short const *>>(v42);
  if ( !a2 || !*a2 || !a1 )
    goto LABEL_45;
  v4 = BuildPath(L"\\\\?\\", a2);
  v45 = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    v7 = LastError < 0;
    if ( LastError > 0 )
      v7 = 1;
    if ( v7 )
    {
      v8 = GetLastError();
      v5 = v8;
      if ( v8 > 0 )
        v5 = (unsigned __int16)v8 | 0x80070000;
      if ( v5 >= 0 )
        goto LABEL_12;
    }
    else
    {
      v5 = -2147467259;
    }
    *(_DWORD *)(a1 + 24) = v5;
    goto LABEL_45;
  }
  v5 = 0;
LABEL_12:
  std::deque<unsigned short const *>::push_back(v39, &v45);
  *(_QWORD *)(a1 + 160) = v39;
  *(_QWORD *)(a1 + 72) = v4;
  ProcessHeap = GetProcessHeap();
  v10 = HeapAlloc(ProcessHeap, 8u, 0x10000u);
  *(_QWORD *)(a1 + 80) = v10;
  *(_DWORD *)(a1 + 88) = 0x8000;
  if ( !v10 )
  {
    *(_DWORD *)(a1 + 88) = 0;
    v11 = GetLastError();
    v12 = CurrentIP();
    v13 = ConstructPartialMsgW(
            0x3000000u,
            "SetupClnEnumDir Failed to allocate buffer to handle hardlinks for [%s]",
            *(const char **)(a1 + 72));
    WdsSetupLogMessageW(
      v13,
      0,
      L"D",
      0,
      1511,
      L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
      L"SetupClnEnumDir",
      v12,
      v11,
      0,
      0);
  }
  while ( 1 )
  {
    v14 = v41;
    if ( !v41 || *(_DWORD *)(a1 + 28) )
      break;
    v15 = v40;
    v33 = 0;
    std::_Iterator_base12::_Adopt((std::_Iterator_base12 *)&v33, (const struct std::_Container_base12 *)v39);
    v34 = v15 + v14;
    std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<unsigned short const *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<unsigned short const *>>>(
      &v35,
      &v33);
    --v36;
    std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<unsigned short const *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<unsigned short const *>>>(
      v37,
      &v35);
    v16 = v37[0];
    if ( v37[0] )
      v16 = *(_QWORD *)v37[0];
    v45 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v16 + 8) + 8 * ((*(_QWORD *)(v16 + 16) - 1LL) & (v38 >> 1)))
                    + 8 * (v38 & 1));
    std::deque<unsigned short const *>::pop_back(v39);
    v18 = EnumeratePathEx(v17, 1);
    if ( v5 < 0 || (v5 = HrBool(v18), v5 < 0) )
    {
      if ( *(int *)(a1 + 24) >= 0 )
        *(_DWORD *)(a1 + 24) = v5;
    }
    std::deque<unsigned short const *>::push_back(v42, &v45);
  }
  while ( 1 )
  {
    v19 = v44;
    if ( !v44 )
      break;
    v20 = v43;
    v35 = 0;
    std::_Iterator_base12::_Adopt((std::_Iterator_base12 *)&v35, (const struct std::_Container_base12 *)v42);
    v36 = v19 + v20;
    std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<unsigned short const *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<unsigned short const *>>>(
      &v33,
      &v35);
    --v34;
    std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<unsigned short const *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<unsigned short const *>>>(
      v37,
      &v33);
    v21 = v37[0];
    if ( v37[0] )
      v21 = *(_QWORD *)v37[0];
    v22 = *(void **)(*(_QWORD *)(*(_QWORD *)(v21 + 8) + 8 * ((*(_QWORD *)(v21 + 16) - 1LL) & (v38 >> 1))) + 8 * (v38 & 1));
    std::deque<unsigned short const *>::pop_back(v42);
    if ( *(_DWORD *)(a1 + 28) || !*(_DWORD *)a1 )
      goto LABEL_30;
    v23 = WdsRemoveDirectoryWithFlags(v22, 32);
    if ( v5 >= 0 )
    {
      v5 = HrBool(v23);
LABEL_30:
      if ( v5 >= 0 )
        goto LABEL_33;
    }
    if ( *(int *)(a1 + 24) >= 0 )
      *(_DWORD *)(a1 + 24) = v5;
LABEL_33:
    if ( v22 )
    {
      v24 = GetProcessHeap();
      HeapFree(v24, 0, v22);
    }
  }
  while ( 1 )
  {
    v25 = v41;
    if ( !v41 )
      break;
    v26 = v40;
    v35 = 0;
    std::_Iterator_base12::_Adopt((std::_Iterator_base12 *)&v35, (const struct std::_Container_base12 *)v39);
    v36 = v25 + v26;
    std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<unsigned short const *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<unsigned short const *>>>(
      &v33,
      &v35);
    --v34;
    std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<unsigned short const *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<unsigned short const *>>>(
      v37,
      &v33);
    v27 = v37[0];
    if ( v37[0] )
      v27 = *(_QWORD *)v37[0];
    v28 = *(void **)(*(_QWORD *)(*(_QWORD *)(v27 + 8) + 8 * ((*(_QWORD *)(v27 + 16) - 1LL) & (v38 >> 1))) + 8 * (v38 & 1));
    std::deque<unsigned short const *>::pop_back(v39);
    if ( v28 )
    {
      v29 = GetProcessHeap();
      HeapFree(v29, 0, v28);
    }
  }
  v30 = *(void **)(a1 + 80);
  if ( v30 )
  {
    v31 = GetProcessHeap();
    if ( HeapFree(v31, 0, v30) )
      *(_QWORD *)(a1 + 80) = 0;
  }
LABEL_45:
  std::deque<unsigned short const *>::~deque<unsigned short const *>(v42);
  return std::deque<unsigned short const *>::~deque<unsigned short const *>(v39);
}

```

## disassembly

```asm
0x180006b48  mov     [rsp-8+arg_0], rbx
0x180006b4d  mov     [rsp-8+arg_10], rsi
0x180006b52  push    rbp
0x180006b53  push    rdi
0x180006b54  push    r14
0x180006b56  lea     rbp, [rsp-47h]
0x180006b5b  sub     rsp, 100h
0x180006b62  mov     rbx, rdx
0x180006b65  mov     r14, rcx
0x180006b68  lea     rcx, [rbp+57h+var_68]
0x180006b6c  call    ??0?$stack@PEBGV?$deque@PEBGV?$allocator@PEBG@std@@@std@@@std@@QEAA@XZ; std::stack<ushort const *>::stack<ushort const *,std::deque<ushort const *>>(void)
0x180006b71  nop
0x180006b72  lea     rcx, [rbp+57h+var_40]
0x180006b76  call    ??0?$stack@PEBGV?$deque@PEBGV?$allocator@PEBG@std@@@std@@@std@@QEAA@XZ; std::stack<ushort const *>::stack<ushort const *,std::deque<ushort const *>>(void)
0x180006b7b  nop
0x180006b7c  test    rbx, rbx
0x180006b7f  jz      loc_180006F46
0x180006b85  xor     eax, eax
0x180006b87  cmp     ax, [rbx]
0x180006b8a  jz      loc_180006F46
0x180006b90  test    r14, r14
0x180006b93  jz      loc_180006F46
0x180006b99  mov     rdx, rbx; STRSAFE_PCNZWCH
0x180006b9c  lea     rcx, pszSrc; "\\\\?\\"
0x180006ba3  call    BuildPath
0x180006ba8  mov     rbx, rax
0x180006bab  mov     [rbp+57h+arg_8], rax
0x180006baf  test    rax, rax
0x180006bb2  jz      short loc_180006BB8
0x180006bb4  xor     esi, esi
0x180006bb6  jmp     short loc_180006BED
0x180006bb8  call    cs:__imp_GetLastError
0x180006bbe  mov     edi, 80070000h
0x180006bc3  test    eax, eax
0x180006bc5  jle     short loc_180006BCE
0x180006bc7  movzx   eax, ax
0x180006bca  or      eax, edi
0x180006bcc  test    eax, eax
0x180006bce  jns     loc_180006F3D
0x180006bd4  call    cs:__imp_GetLastError
0x180006bda  mov     esi, eax
0x180006bdc  test    eax, eax
0x180006bde  jle     short loc_180006BE5
0x180006be0  movzx   esi, ax
0x180006be3  or      esi, edi
0x180006be5  test    esi, esi
0x180006be7  js      loc_180006F42
0x180006bed  lea     rdx, [rbp+57h+arg_8]
0x180006bf1  lea     rcx, [rbp+57h+var_68]
0x180006bf5  call    ?push_back@?$deque@PEBGV?$allocator@PEBG@std@@@std@@QEAAXAEBQEBG@Z; std::deque<ushort const *>::push_back(ushort const * const &)
0x180006bfa  lea     rax, [rbp+57h+var_68]
0x180006bfe  mov     [r14+0A0h], rax
0x180006c05  mov     [r14+48h], rbx
0x180006c09  call    cs:__imp_GetProcessHeap
0x180006c0f  mov     rcx, rax; hHeap
0x180006c12  mov     edx, 8; dwFlags
0x180006c17  mov     r8d, 10000h; dwBytes
0x180006c1d  call    cs:__imp_HeapAlloc
0x180006c23  mov     [r14+50h], rax
0x180006c27  mov     dword ptr [r14+58h], 8000h
0x180006c2f  test    rax, rax
0x180006c32  jnz     short loc_180006CAD
0x180006c34  mov     [r14+58h], eax
0x180006c38  call    cs:__imp_GetLastError
0x180006c3e  mov     edi, eax
0x180006c40  call    cs:__imp_CurrentIP
0x180006c46  mov     rbx, rax
0x180006c49  mov     r8, [r14+48h]
0x180006c4d  lea     rdx, aSetupclnenumdi; "SetupClnEnumDir Failed to allocate buff"...
0x180006c54  mov     ecx, 3000000h; unsigned int
0x180006c59  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180006c5e  mov     [rsp+110h+var_C0], 0
0x180006c66  mov     [rsp+110h+var_C8], 0
0x180006c6f  mov     [rsp+110h+var_D0], edi
0x180006c73  mov     [rsp+110h+var_D8], rbx
0x180006c78  lea     rcx, aSetupclnenumdi_0; "SetupClnEnumDir"
0x180006c7f  mov     [rsp+110h+var_E0], rcx
0x180006c84  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x180006c8b  mov     [rsp+110h+var_E8], rcx
0x180006c90  mov     [rsp+110h+var_F0], 5E7h
0x180006c98  xor     r9d, r9d
0x180006c9b  lea     r8, aD; "D"
0x180006ca2  xor     edx, edx
0x180006ca4  mov     rcx, rax
0x180006ca7  call    cs:__imp_WdsSetupLogMessageW
0x180006cad  mov     rdi, [rbp+57h+var_48]
0x180006cb1  test    rdi, rdi
0x180006cb4  jz      loc_180006D90
0x180006cba  cmp     dword ptr [r14+1Ch], 0
0x180006cbf  jnz     loc_180006D90
0x180006cc5  mov     rbx, [rbp+57h+var_50]
0x180006cc9  xorps   xmm0, xmm0
0x180006ccc  movdqu  [rbp+57h+var_B0], xmm0
0x180006cd1  lea     rdx, [rbp+57h+var_68]; struct std::_Container_base12 *
0x180006cd5  lea     rcx, [rbp+57h+var_B0]; this
0x180006cd9  call    ?_Adopt@_Iterator_base12@std@@QEAAXPEBU_Container_base12@2@@Z; std::_Iterator_base12::_Adopt(std::_Container_base12 const *)
0x180006cde  lea     rax, [rbx+rdi]
0x180006ce2  mov     [rbp+57h+var_A0], rax
0x180006ce6  lea     rdx, [rbp+57h+var_B0]
0x180006cea  lea     rcx, [rbp+57h+var_98]
0x180006cee  call    ??0?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@PEBG@std@@@std@@@std@@QEAA@AEBV01@@Z; std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ushort const *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ushort const *>>>(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ushort const *>>> const &)
0x180006cf3  dec     [rbp+57h+var_88]
0x180006cf7  lea     rdx, [rbp+57h+var_98]
0x180006cfb  lea     rcx, [rbp+57h+var_80]
0x180006cff  call    ??0?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@PEBG@std@@@std@@@std@@QEAA@AEBV01@@Z; std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ushort const *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ushort const *>>>(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ushort const *>>> const &)
0x180006d04  mov     rdx, [rbp+57h+var_80]
0x180006d08  test    rdx, rdx
0x180006d0b  jz      short loc_180006D10
0x180006d0d  mov     rdx, [rdx]
0x180006d10  mov     r10, [rbp+57h+var_70]
0x180006d14  mov     rcx, r10
0x180006d17  shr     rcx, 1
0x180006d1a  mov     rax, [rdx+10h]
0x180006d1e  dec     rax
0x180006d21  and     rcx, rax
0x180006d24  mov     rax, [rdx+8]
0x180006d28  and     r10d, 1
0x180006d2c  mov     rax, [rax+rcx*8]
0x180006d30  mov     r10, [rax+r10*8]
0x180006d34  mov     [rbp+57h+arg_8], r10
0x180006d38  lea     rcx, [rbp+57h+var_68]
0x180006d3c  call    ?pop_back@?$deque@PEBGV?$allocator@PEBG@std@@@std@@QEAAXXZ; std::deque<ushort const *>::pop_back(void)
0x180006d41  mov     [rsp+110h+var_F0], 1; int
0x180006d49  mov     r9, r14
0x180006d4c  lea     r8, SetupClnEnumFileCallback
0x180006d53  lea     rdx, SetupClnEnumDirCallback
0x180006d5a  mov     rcx, r10; lpFileName
0x180006d5d  call    EnumeratePathEx
0x180006d62  test    esi, esi
0x180006d64  js      short loc_180006D73
0x180006d66  mov     ecx, eax; int
0x180006d68  call    ?HrBool@@YAJH@Z; HrBool(int)
0x180006d6d  mov     esi, eax
0x180006d6f  test    eax, eax
0x180006d71  jns     short loc_180006D7E
0x180006d73  cmp     dword ptr [r14+18h], 0
0x180006d78  jl      short loc_180006D7E
0x180006d7a  mov     [r14+18h], esi
0x180006d7e  lea     rdx, [rbp+57h+arg_8]
0x180006d82  lea     rcx, [rbp+57h+var_40]
0x180006d86  call    ?push_back@?$deque@PEBGV?$allocator@PEBG@std@@@std@@QEAAXAEBQEBG@Z; std::deque<ushort const *>::push_back(ushort const * const &)
0x180006d8b  jmp     loc_180006CAD
0x180006d90  mov     rdi, [rbp+57h+var_20]
0x180006d94  test    rdi, rdi
0x180006d97  jz      loc_180006E6C
0x180006d9d  mov     rbx, [rbp+57h+var_28]
0x180006da1  xorps   xmm0, xmm0
0x180006da4  movdqu  [rbp+57h+var_98], xmm0
0x180006da9  lea     rdx, [rbp+57h+var_40]; struct std::_Container_base12 *
0x180006dad  lea     rcx, [rbp+57h+var_98]; this
0x180006db1  call    ?_Adopt@_Iterator_base12@std@@QEAAXPEBU_Container_base12@2@@Z; std::_Iterator_base12::_Adopt(std::_Container_base12 const *)
0x180006db6  lea     rax, [rdi+rbx]
0x180006dba  mov     [rbp+57h+var_88], rax
0x180006dbe  lea     rdx, [rbp+57h+var_98]
0x180006dc2  lea     rcx, [rbp+57h+var_B0]
0x180006dc6  call    ??0?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@PEBG@std@@@std@@@std@@QEAA@AEBV01@@Z; std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ushort const *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ushort const *>>>(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ushort const *>>> const &)
0x180006dcb  dec     [rbp+57h+var_A0]
0x180006dcf  lea     rdx, [rbp+57h+var_B0]
0x180006dd3  lea     rcx, [rbp+57h+var_80]
0x180006dd7  call    ??0?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@PEBG@std@@@std@@@std@@QEAA@AEBV01@@Z; std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ushort const *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ushort const *>>>(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ushort const *>>> const &)
0x180006ddc  mov     r8, [rbp+57h+var_80]
0x180006de0  test    r8, r8
0x180006de3  jz      short loc_180006DE8
0x180006de5  mov     r8, [r8]
0x180006de8  mov     rdx, [rbp+57h+var_70]
0x180006dec  mov     rcx, rdx
0x180006def  shr     rcx, 1
0x180006df2  mov     rax, [r8+10h]
0x180006df6  dec     rax
0x180006df9  and     rcx, rax
0x180006dfc  mov     rax, [r8+8]
0x180006e00  and     edx, 1
0x180006e03  mov     rax, [rax+rcx*8]
0x180006e07  mov     rbx, [rax+rdx*8]
0x180006e0b  lea     rcx, [rbp+57h+var_40]
0x180006e0f  call    ?pop_back@?$deque@PEBGV?$allocator@PEBG@std@@@std@@QEAAXXZ; std::deque<ushort const *>::pop_back(void)
0x180006e14  cmp     dword ptr [r14+1Ch], 0
0x180006e19  jnz     short loc_180006E3B
0x180006e1b  cmp     dword ptr [r14], 0
0x180006e1f  jz      short loc_180006E3B
0x180006e21  mov     edx, 20h ; ' '
0x180006e26  mov     rcx, rbx
0x180006e29  call    WdsRemoveDirectoryWithFlags
0x180006e2e  test    esi, esi
0x180006e30  js      short loc_180006E3F
0x180006e32  mov     ecx, eax; int
0x180006e34  call    ?HrBool@@YAJH@Z; HrBool(int)
0x180006e39  mov     esi, eax
0x180006e3b  test    esi, esi
0x180006e3d  jns     short loc_180006E4A
0x180006e3f  cmp     dword ptr [r14+18h], 0
0x180006e44  jl      short loc_180006E4A
0x180006e46  mov     [r14+18h], esi
0x180006e4a  test    rbx, rbx
0x180006e4d  jz      loc_180006D90
0x180006e53  call    cs:__imp_GetProcessHeap
0x180006e59  mov     r8, rbx; lpMem
0x180006e5c  xor     edx, edx; dwFlags
0x180006e5e  mov     rcx, rax; hHeap
0x180006e61  call    cs:__imp_HeapFree
0x180006e67  jmp     loc_180006D90
0x180006e6c  mov     rdi, [rbp+57h+var_48]
0x180006e70  test    rdi, rdi
0x180006e73  jz      loc_180006F12
0x180006e79  mov     rbx, [rbp+57h+var_50]
0x180006e7d  xorps   xmm0, xmm0
0x180006e80  movdqu  [rbp+57h+var_98], xmm0
0x180006e85  lea     rdx, [rbp+57h+var_68]; struct std::_Container_base12 *
0x180006e89  lea     rcx, [rbp+57h+var_98]; this
0x180006e8d  call    ?_Adopt@_Iterator_base12@std@@QEAAXPEBU_Container_base12@2@@Z; std::_Iterator_base12::_Adopt(std::_Container_base12 const *)
0x180006e92  lea     rax, [rdi+rbx]
0x180006e96  mov     [rbp+57h+var_88], rax
0x180006e9a  lea     rdx, [rbp+57h+var_98]
0x180006e9e  lea     rcx, [rbp+57h+var_B0]
0x180006ea2  call    ??0?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@PEBG@std@@@std@@@std@@QEAA@AEBV01@@Z; std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ushort const *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ushort const *>>>(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ushort const *>>> const &)
0x180006ea7  dec     [rbp+57h+var_A0]
0x180006eab  lea     rdx, [rbp+57h+var_B0]
0x180006eaf  lea     rcx, [rbp+57h+var_80]
0x180006eb3  call    ??0?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@PEBG@std@@@std@@@std@@QEAA@AEBV01@@Z; std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ushort const *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ushort const *>>>(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ushort const *>>> const &)
0x180006eb8  mov     r8, [rbp+57h+var_80]
0x180006ebc  test    r8, r8
0x180006ebf  jz      short loc_180006EC4
0x180006ec1  mov     r8, [r8]
0x180006ec4  mov     rdx, [rbp+57h+var_70]
0x180006ec8  mov     rcx, rdx
0x180006ecb  shr     rcx, 1
0x180006ece  mov     rax, [r8+10h]
0x180006ed2  dec     rax
0x180006ed5  and     rcx, rax
0x180006ed8  mov     rax, [r8+8]
0x180006edc  and     edx, 1
0x180006edf  mov     rax, [rax+rcx*8]
0x180006ee3  mov     rbx, [rax+rdx*8]
0x180006ee7  lea     rcx, [rbp+57h+var_68]
0x180006eeb  call    ?pop_back@?$deque@PEBGV?$allocator@PEBG@std@@@std@@QEAAXXZ; std::deque<ushort const *>::pop_back(void)
0x180006ef0  test    rbx, rbx
0x180006ef3  jz      loc_180006E6C
0x180006ef9  call    cs:__imp_GetProcessHeap
0x180006eff  mov     r8, rbx; lpMem
0x180006f02  xor     edx, edx; dwFlags
0x180006f04  mov     rcx, rax; hHeap
0x180006f07  call    cs:__imp_HeapFree
0x180006f0d  jmp     loc_180006E6C
0x180006f12  mov     rbx, [r14+50h]
0x180006f16  test    rbx, rbx
0x180006f19  jz      short loc_180006F46
0x180006f1b  call    cs:__imp_GetProcessHeap
0x180006f21  mov     r8, rbx; lpMem
0x180006f24  xor     edx, edx; dwFlags
0x180006f26  mov     rcx, rax; hHeap
0x180006f29  call    cs:__imp_HeapFree
0x180006f2f  test    eax, eax
0x180006f31  jz      short loc_180006F46
0x180006f33  mov     qword ptr [r14+50h], 0
0x180006f3b  jmp     short loc_180006F46
0x180006f3d  mov     esi, 80004005h
0x180006f42  mov     [r14+18h], esi
0x180006f46  lea     rcx, [rbp+57h+var_40]
0x180006f4a  call    ??1?$deque@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::deque<ushort const *>::~deque<ushort const *>(void)
0x180006f4f  nop
0x180006f50  lea     rcx, [rbp+57h+var_68]
0x180006f54  call    ??1?$deque@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::deque<ushort const *>::~deque<ushort const *>(void)
0x180006f59  lea     r11, [rsp+110h+var_10]
0x180006f61  mov     rbx, [r11+20h]
0x180006f65  mov     rsi, [r11+30h]
0x180006f69  mov     rsp, r11
0x180006f6c  pop     r14
0x180006f6e  pop     rdi
0x180006f6f  pop     rbp
0x180006f70  retn
```
