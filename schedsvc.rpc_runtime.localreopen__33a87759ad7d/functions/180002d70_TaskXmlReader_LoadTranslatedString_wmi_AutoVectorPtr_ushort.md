# TaskXmlReader::LoadTranslatedString(wmi::AutoVectorPtr<ushort> &)

- ea: `0x180002d70`
- end: `0x18000320e`
- name: `?LoadTranslatedString@TaskXmlReader@@SAJAEAV?$AutoVectorPtr@G@wmi@@@Z`
- size: `1182`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x180003220`

## callees

- `0x180002d70`
- `0x18001a260`
- `0x18005790c`

## import_xrefs

- `msvcrt!wcschr` at `0x180002dd8`
- `msvcrt!wcschr` at `0x180002dea`
- `msvcrt!wcschr` at `0x180002dd8`
- `msvcrt!wcschr` at `0x180002dea`
- `msvcrt!_wtol` at `0x180002f75`
- `msvcrt!_wtol` at `0x180002f75`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003038`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800031e0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003038`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800031e0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180002fd4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180002fd4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000301a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000301a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000304b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000305e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003072`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003095`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000304b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000305e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003072`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003095`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002e3a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002ef2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002f95`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002ff9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002e3a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002ef2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002f95`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002ff9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180002fbb`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180002fbb`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall TaskXmlReader::LoadTranslatedString(const wchar_t **a1)
{
  const wchar_t *v2; // rcx
  __int64 v3; // rsi
  wchar_t *v4; // rbx
  wchar_t *v5; // rax
  wchar_t *v6; // r14
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rdi
  SIZE_T v9; // rax
  WCHAR *v10; // rax
  WCHAR *v11; // r9
  WCHAR *v12; // rcx
  WCHAR *v13; // rdx
  int v14; // r12d
  int v15; // r8d
  WCHAR v16; // ax
  unsigned __int64 v17; // rbx
  unsigned __int64 v18; // rdi
  SIZE_T v19; // rax
  _WORD *v20; // rax
  void *v21; // r15
  __int16 *v22; // rcx
  _WORD *v23; // rdx
  __int16 v24; // ax
  UINT v25; // r14d
  WCHAR *v26; // rax
  WCHAR *v27; // rbx
  HMODULE Library; // rdi
  WCHAR *v29; // rax
  WCHAR *v30; // rsi
  WCHAR *v32; // rcx
  void **pExceptionObject; // [rsp+28h] [rbp-40h] BYREF
  char v34; // [rsp+30h] [rbp-38h]
  const unsigned __int16 *v35; // [rsp+38h] [rbp-30h]
  __int64 v36; // [rsp+40h] [rbp-28h]
  __int64 v37; // [rsp+48h] [rbp-20h]
  int v38; // [rsp+50h] [rbp-18h]
  __int64 v39; // [rsp+54h] [rbp-14h]
  WCHAR *lpSrc; // [rsp+B0h] [rbp+48h]

  v2 = *a1;
  v3 = -1;
  do
    ++v3;
  while ( v2[v3] );
  if ( (unsigned int)v3 < 8 )
    return 1;
  if ( *v2 != 36 )
    return 1;
  if ( v2[1] != 40 )
    return 1;
  if ( v2[2] != 64 )
    return 1;
  v4 = wcschr(v2, 0x2Cu);
  v5 = wcschr(*a1, 0x2Du);
  v6 = v5;
  if ( !v4 || !v5 || (char *)v5 - (char *)v4 != 2 )
    return 1;
  v7 = v4 - *a1 - 3;
  v8 = v7 + 1;
  v9 = 2 * (v7 + 1);
  if ( !is_mul_ok(v7 + 1, 2u) )
    v9 = -1;
  v10 = (WCHAR *)HeapAlloc(g_PrivateHeap, 0, v9);
  v11 = v10;
  lpSrc = v10;
  if ( !v10 )
  {
    v34 = 0;
    v35 = &qword_1800A4718;
    v36 = 0;
    v37 = 0;
    v38 = 14;
    v39 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  if ( v7 == -1 )
    goto LABEL_48;
  if ( v8 > 0x7FFFFFFF || v7 > 0x7FFFFFFE )
  {
    *v10 = 0;
LABEL_48:
    v32 = v11;
    goto LABEL_46;
  }
  v12 = (WCHAR *)(*a1 + 3);
  v13 = v10;
  v14 = 0;
  v15 = 0;
  while ( v7 )
  {
    v16 = *v12;
    if ( !*v12 )
    {
      if ( !v8 )
      {
LABEL_20:
        --v13;
        v15 = -2147024774;
        break;
      }
      break;
    }
    ++v12;
    *v13++ = v16;
    --v7;
    if ( !--v8 )
      goto LABEL_20;
  }
  *v13 = 0;
  if ( v15 < 0 )
    goto LABEL_48;
  v17 = (unsigned int)v3 - (v6 - *a1);
  v18 = v17 + 1;
  v19 = 2 * (v17 + 1);
  if ( !is_mul_ok(v17 + 1, 2u) )
    v19 = -1;
  v20 = HeapAlloc(g_PrivateHeap, 0, v19);
  v21 = v20;
  if ( !v20 )
  {
    v34 = 0;
    v35 = &qword_1800A4718;
    v36 = 0;
    v37 = 0;
    v38 = 14;
    v39 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  if ( v17 == -1 )
    goto LABEL_45;
  if ( v18 > 0x7FFFFFFF || v17 > 0x7FFFFFFE )
  {
    *v20 = 0;
LABEL_45:
    operator delete(v21);
    v32 = lpSrc;
LABEL_46:
    operator delete(v32);
    return 1;
  }
  v22 = (__int16 *)(v6 + 1);
  v23 = v20;
  while ( v17 )
  {
    v24 = *v22;
    if ( !*v22 )
    {
      if ( !v18 )
      {
LABEL_33:
        --v23;
        v14 = -2147024774;
        break;
      }
      break;
    }
    ++v22;
    *v23++ = v24;
    --v17;
    if ( !--v18 )
      goto LABEL_33;
  }
  *v23 = 0;
  if ( v14 < 0 )
    goto LABEL_45;
  v25 = _wtol((const wchar_t *)v21);
  if ( !v25 )
    goto LABEL_45;
  v26 = (WCHAR *)HeapAlloc(g_PrivateHeap, 0, 0x208u);
  v27 = v26;
  if ( !v26 )
  {
    v34 = 0;
    v35 = &qword_1800A4718;
    v36 = 0;
    v37 = 0;
    v38 = 14;
    v39 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  if ( !ExpandEnvironmentStringsW(lpSrc, v26, 0x103u) || (Library = LoadLibraryExW(v27, 0, 2u)) == 0 )
  {
    operator delete(v27);
    operator delete(v21);
    v32 = lpSrc;
    goto LABEL_46;
  }
  v29 = (WCHAR *)HeapAlloc(g_PrivateHeap, 0, 0xA000u);
  v30 = v29;
  if ( !v29 )
  {
    v34 = 0;
    v35 = &qword_1800A4718;
    v36 = 0;
    v37 = 0;
    v38 = 14;
    v39 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  if ( !LoadStringW(Library, v25, v29, 20479) )
  {
    operator delete(v30);
    FreeLibrary(Library);
    operator delete(v27);
    goto LABEL_45;
  }
  if ( *a1 )
    HeapFree(g_PrivateHeap, 0, (LPVOID)*a1);
  *a1 = v30;
  FreeLibrary(Library);
  HeapFree(g_PrivateHeap, 0, v27);
  HeapFree(g_PrivateHeap, 0, v21);
  HeapFree(g_PrivateHeap, 0, lpSrc);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180002d70  push    rbp
0x180002d72  push    rbx
0x180002d73  push    rsi
0x180002d74  push    rdi
0x180002d75  push    r12
0x180002d77  push    r13
0x180002d79  push    r14
0x180002d7b  push    r15
0x180002d7d  mov     rbp, rsp
0x180002d80  sub     rsp, 68h
0x180002d84  mov     r13, rcx
0x180002d87  mov     rcx, [rcx]; Str
0x180002d8a  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180002d91  mov     rsi, r15
0x180002d94  inc     rsi
0x180002d97  cmp     word ptr [rcx+rsi*2], 0
0x180002d9c  jnz     short loc_180002D94
0x180002d9e  cmp     esi, 8
0x180002da1  jb      loc_1800030AF
0x180002da7  mov     eax, 24h ; '$'
0x180002dac  cmp     ax, [rcx]
0x180002daf  jnz     loc_1800030AF
0x180002db5  mov     eax, 28h ; '('
0x180002dba  cmp     ax, [rcx+2]
0x180002dbe  jnz     loc_1800030AF
0x180002dc4  mov     eax, 40h ; '@'
0x180002dc9  cmp     ax, [rcx+4]
0x180002dcd  jnz     loc_1800030AF
0x180002dd3  mov     edx, 2Ch ; ','; Ch
0x180002dd8  call    cs:__imp_wcschr
0x180002dde  mov     rbx, rax
0x180002de1  mov     edx, 2Dh ; '-'; Ch
0x180002de6  mov     rcx, [r13+0]; Str
0x180002dea  call    cs:__imp_wcschr
0x180002df0  mov     r14, rax
0x180002df3  test    rbx, rbx
0x180002df6  jz      loc_1800030AF
0x180002dfc  test    rax, rax
0x180002dff  jz      loc_1800030AF
0x180002e05  mov     rcx, rax
0x180002e08  sub     rcx, rbx
0x180002e0b  cmp     rcx, 2
0x180002e0f  jnz     loc_1800030AF
0x180002e15  sub     rbx, [r13+0]
0x180002e19  sar     rbx, 1
0x180002e1c  add     rbx, 0FFFFFFFFFFFFFFFDh
0x180002e20  lea     rdi, [rbx+1]
0x180002e24  mov     rax, rcx
0x180002e27  mul     rdi
0x180002e2a  cmovb   rax, r15
0x180002e2e  mov     r8, rax; dwBytes
0x180002e31  xor     edx, edx; dwFlags
0x180002e33  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180002e3a  call    cs:__imp_HeapAlloc
0x180002e40  mov     r9, rax
0x180002e43  mov     [rbp+lpSrc], rax
0x180002e47  test    rax, rax
0x180002e4a  jz      loc_1800030BB
0x180002e50  mov     [rbp+arg_8], rax
0x180002e54  test    rdi, rdi
0x180002e57  jz      loc_1800030B6
0x180002e5d  cmp     rdi, 7FFFFFFFh
0x180002e64  ja      loc_1800030FB
0x180002e6a  cmp     rbx, 7FFFFFFEh
0x180002e71  ja      loc_1800030FB
0x180002e77  mov     rcx, [r13+0]
0x180002e7b  add     rcx, 6
0x180002e7f  mov     rdx, rax
0x180002e82  xor     r12d, r12d
0x180002e85  mov     r8d, r12d
0x180002e88  test    rbx, rbx
0x180002e8b  jz      short loc_180002EBA
0x180002e8d  movzx   eax, word ptr [rcx]
0x180002e90  test    ax, ax
0x180002e93  jz      short loc_180002EB5
0x180002e95  add     rcx, 2
0x180002e99  mov     [rdx], ax
0x180002e9c  add     rdx, 2
0x180002ea0  dec     rbx
0x180002ea3  sub     rdi, 1
0x180002ea7  jnz     short loc_180002E88
0x180002ea9  sub     rdx, 2
0x180002ead  mov     r8d, 8007007Ah
0x180002eb3  jmp     short loc_180002EBA
0x180002eb5  test    rdi, rdi
0x180002eb8  jz      short loc_180002EA9
0x180002eba  mov     [rdx], r12w
0x180002ebe  test    r8d, r8d
0x180002ec1  js      loc_1800030B6
0x180002ec7  mov     rax, r14
0x180002eca  sub     rax, [r13+0]
0x180002ece  sar     rax, 1
0x180002ed1  mov     ebx, esi
0x180002ed3  sub     rbx, rax
0x180002ed6  lea     rdi, [rbx+1]
0x180002eda  mov     eax, 2
0x180002edf  mul     rdi
0x180002ee2  cmovb   rax, r15
0x180002ee6  mov     r8, rax; dwBytes
0x180002ee9  xor     edx, edx; dwFlags
0x180002eeb  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180002ef2  call    cs:__imp_HeapAlloc
0x180002ef8  mov     r15, rax
0x180002efb  test    rax, rax
0x180002efe  jz      loc_180003103
0x180002f04  mov     [rbp+arg_10], rax
0x180002f08  test    rdi, rdi
0x180002f0b  jz      loc_18000309D
0x180002f11  cmp     rdi, 7FFFFFFFh
0x180002f18  ja      loc_180003145
0x180002f1e  cmp     rbx, 7FFFFFFEh
0x180002f25  ja      loc_180003145
0x180002f2b  lea     rcx, [r14+2]
0x180002f2f  mov     rdx, rax
0x180002f32  test    rbx, rbx
0x180002f35  jz      short loc_180002F64
0x180002f37  movzx   eax, word ptr [rcx]
0x180002f3a  test    ax, ax
0x180002f3d  jz      short loc_180002F5F
0x180002f3f  add     rcx, 2
0x180002f43  mov     [rdx], ax
0x180002f46  add     rdx, 2
0x180002f4a  dec     rbx
0x180002f4d  sub     rdi, 1
0x180002f51  jnz     short loc_180002F32
0x180002f53  sub     rdx, 2
0x180002f57  mov     r12d, 8007007Ah
0x180002f5d  jmp     short loc_180002F64
0x180002f5f  test    rdi, rdi
0x180002f62  jz      short loc_180002F53
0x180002f64  xor     edi, edi
0x180002f66  mov     [rdx], di
0x180002f69  test    r12d, r12d
0x180002f6c  js      loc_18000309D
0x180002f72  mov     rcx, r15; String
0x180002f75  call    cs:__imp__wtol
0x180002f7b  mov     r14d, eax
0x180002f7e  test    eax, eax
0x180002f80  jz      loc_18000309D
0x180002f86  xor     edx, edx; dwFlags
0x180002f88  mov     r8d, 208h; dwBytes
0x180002f8e  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180002f95  call    cs:__imp_HeapAlloc
0x180002f9b  mov     rbx, rax
0x180002f9e  test    rax, rax
0x180002fa1  jz      loc_18000314E
0x180002fa7  mov     [rbp+arg_18], rax
0x180002fab  mov     r8d, 103h; nSize
0x180002fb1  mov     rdx, rax; lpDst
0x180002fb4  mov     rsi, [rbp+lpSrc]
0x180002fb8  mov     rcx, rsi; lpSrc
0x180002fbb  call    cs:__imp_ExpandEnvironmentStringsW
0x180002fc1  test    eax, eax
0x180002fc3  jz      loc_1800031F4
0x180002fc9  xor     edx, edx; hFile
0x180002fcb  mov     r8d, 2; dwFlags
0x180002fd1  mov     rcx, rbx; lpLibFileName
0x180002fd4  call    cs:__imp_LoadLibraryExW
0x180002fda  mov     rdi, rax
0x180002fdd  test    rax, rax
0x180002fe0  jz      loc_1800031F4
0x180002fe6  mov     [rbp+var_48], rax
0x180002fea  xor     edx, edx; dwFlags
0x180002fec  mov     r8d, 0A000h; dwBytes
0x180002ff2  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180002ff9  call    cs:__imp_HeapAlloc
0x180002fff  mov     rsi, rax
0x180003002  test    rax, rax
0x180003005  jz      loc_180003190
0x18000300b  mov     r9d, 4FFFh; cchBufferMax
0x180003011  mov     r8, rax; lpBuffer
0x180003014  mov     edx, r14d; uID
0x180003017  mov     rcx, rdi; hInstance
0x18000301a  call    cs:__imp_LoadStringW
0x180003020  test    eax, eax
0x180003022  jz      loc_1800031D4
0x180003028  mov     r8, [r13+0]; lpMem
0x18000302c  test    r8, r8
0x18000302f  jnz     short loc_18000308C
0x180003031  mov     [r13+0], rsi
0x180003035  mov     rcx, rdi; hLibModule
0x180003038  call    cs:__imp_FreeLibrary
0x18000303e  nop
0x18000303f  mov     r8, rbx; lpMem
0x180003042  xor     edx, edx; dwFlags
0x180003044  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18000304b  call    cs:__imp_HeapFree
0x180003051  nop
0x180003052  mov     r8, r15; lpMem
0x180003055  xor     edx, edx; dwFlags
0x180003057  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18000305e  call    cs:__imp_HeapFree
0x180003064  nop
0x180003065  mov     r8, [rbp+lpSrc]; lpMem
0x180003069  xor     edx, edx; dwFlags
0x18000306b  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180003072  call    cs:__imp_HeapFree
0x180003078  mov     eax, r12d
0x18000307b  add     rsp, 68h
0x18000307f  pop     r15
0x180003081  pop     r14
0x180003083  pop     r13
0x180003085  pop     r12
0x180003087  pop     rdi
0x180003088  pop     rsi
0x180003089  pop     rbx
0x18000308a  pop     rbp
0x18000308b  retn
0x18000308c  xor     edx, edx; dwFlags
0x18000308e  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180003095  call    cs:__imp_HeapFree
0x18000309b  jmp     short loc_180003031
0x18000309d  mov     rcx, r15; void *
0x1800030a0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800030a5  nop
0x1800030a6  mov     rcx, [rbp+lpSrc]; void *
0x1800030aa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800030af  mov     eax, 1
0x1800030b4  jmp     short loc_18000307B
0x1800030b6  mov     rcx, r9
0x1800030b9  jmp     short loc_1800030AA
0x1800030bb  mov     [rbp+var_38], 0
0x1800030bf  lea     rax, qword_1800A4718
0x1800030c6  mov     [rbp+var_30], rax
0x1800030ca  xor     eax, eax
0x1800030cc  mov     [rbp+var_28], rax
0x1800030d0  mov     [rbp+var_20], rax
0x1800030d4  mov     [rbp+var_18], 0Eh
0x1800030db  mov     [rbp+var_14], r15
0x1800030df  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800030e6  mov     [rbp+pExceptionObject], rax
0x1800030ea  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x1800030f1  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800030f5  call    _CxxThrowException_0
0x1800030fb  xor     eax, eax
0x1800030fd  mov     [r9], ax
0x180003101  jmp     short loc_1800030B6
0x180003103  mov     [rbp+var_38], r12b
0x180003107  lea     rax, qword_1800A4718
0x18000310e  mov     [rbp+var_30], rax
0x180003112  mov     [rbp+var_28], r12
0x180003116  mov     [rbp+var_20], r12
0x18000311a  mov     [rbp+var_18], 0Eh
0x180003121  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x180003129  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180003130  mov     [rbp+pExceptionObject], rax
0x180003134  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18000313b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000313f  call    _CxxThrowException_0
0x180003145  mov     [rax], r12w
0x180003149  jmp     loc_18000309D
0x18000314e  mov     [rbp+var_38], dil
0x180003152  lea     rax, qword_1800A4718
0x180003159  mov     [rbp+var_30], rax
0x18000315d  mov     [rbp+var_28], rdi
0x180003161  mov     [rbp+var_20], rdi
0x180003165  mov     [rbp+var_18], 0Eh
0x18000316c  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x180003174  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000317b  mov     [rbp+pExceptionObject], rax
0x18000317f  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180003186  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000318a  call    _CxxThrowException_0
0x180003190  mov     [rbp+var_38], 0
0x180003194  lea     rax, qword_1800A4718
0x18000319b  mov     [rbp+var_30], rax
0x18000319f  xor     eax, eax
0x1800031a1  mov     [rbp+var_28], rax
0x1800031a5  mov     [rbp+var_20], rax
0x1800031a9  mov     [rbp+var_18], 0Eh
0x1800031b0  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x1800031b8  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800031bf  mov     [rbp+pExceptionObject], rax
0x1800031c3  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x1800031ca  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800031ce  call    _CxxThrowException_0
0x1800031d4  mov     rcx, rsi; void *
0x1800031d7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800031dc  nop
0x1800031dd  mov     rcx, rdi; hLibModule
0x1800031e0  call    cs:__imp_FreeLibrary
0x1800031e6  nop
0x1800031e7  mov     rcx, rbx; void *
0x1800031ea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800031ef  jmp     loc_18000309D
0x1800031f4  mov     rcx, rbx; void *
0x1800031f7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800031fc  nop
0x1800031fd  mov     rcx, r15; void *
0x180003200  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003205  nop
0x180003206  mov     rcx, rsi
0x180003209  jmp     loc_1800030AA
```
