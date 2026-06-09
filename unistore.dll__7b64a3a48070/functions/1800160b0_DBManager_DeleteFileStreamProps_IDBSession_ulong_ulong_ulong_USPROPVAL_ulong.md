# DBManager::DeleteFileStreamProps(IDBSession *,ulong,ulong,ulong,_USPROPVAL *,ulong *)

- ea: `0x1800160b0`
- end: `0x180016355`
- name: `?DeleteFileStreamProps@DBManager@@SAJPEAVIDBSession@@KKKPEAU_USPROPVAL@@PEAK@Z`
- size: `677`
- prototype: `__int64 __fastcall(struct IDBSession *, unsigned int, unsigned int, __int64, struct _USPROPVAL *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task`

## callers

- `0x180033ebc`

## callees

- `0x1800068f0`
- `0x180014bd0`
- `0x1800160b0`
- `0x18001635c`
- `0x180029be0`
- `0x180032170`
- `0x180061ef0`
- `0x18006f180`
- `0x1800c50f0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016263`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016273`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800162a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800162f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016263`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016273`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800162a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800162f9`

## string_xrefs

- `0x180016109`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18001628a`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x1800162b5`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x1800162df`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18001630e`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180016339`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`

## pseudocode

```c
__int64 __fastcall DBManager::DeleteFileStreamProps(
        struct IDBSession *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        struct _USPROPVAL *a5)
{
  unsigned int v5; // esi
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // r13d
  int v12; // eax
  unsigned int v13; // esi
  int DefaultStreamRootPath; // eax
  unsigned int v15; // edi
  __int64 i; // rdi
  int v17; // eax
  unsigned int v18; // r9d
  int v19; // eax
  __int64 v20; // rcx
  HLOCAL v22; // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v24; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v25[264]; // [rsp+60h] [rbp-A0h] BYREF

  v5 = a3;
  v24 = 0;
  if ( !a1 || !a5 )
  {
    Log_UnistoreHREvent_0(
      2147942487LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      3152);
    return 2147942487LL;
  }
  if ( !(unsigned int)IsFileStreamSupportedInTable(a2) )
    Log_AssertionEvent(
      v20,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      3154);
  v11 = (*(__int64 (__fastcall **)(struct IDBSession *))(*(_QWORD *)a1 + 112LL))(a1);
  if ( v11 )
  {
    v12 = (*(__int64 (__fastcall **)(struct IDBSession *, unsigned __int16 **))(*(_QWORD *)a1 + 128LL))(a1, &v24);
    v13 = v12;
    if ( v12 < 0 )
    {
      Log_UnistoreHREvent_0(
        (unsigned int)v12,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        3160);
      return v13;
    }
    (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)a1 + 152LL))(a1);
    v5 = a3;
  }
  DefaultStreamRootPath = StreamHelper::GetDefaultStreamRootPath(v25, v9, v10);
  v15 = DefaultStreamRootPath;
  if ( DefaultStreamRootPath < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)DefaultStreamRootPath,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      3167);
    return v15;
  }
  for ( i = 0; ; i = 1 )
  {
    if ( (_DWORD)i )
      return 0;
    v22 = 0;
    v17 = StreamHelper::BuildStreamPropertyFilePath(
            v25,
            a2,
            v5,
            *((_DWORD *)a5 + 6 * i),
            0,
            0,
            (unsigned __int16 **)&v22);
    v13 = v17;
    if ( v17 < 0 )
    {
      Log_UnistoreHREvent_0(
        (unsigned int)v17,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        3174);
      goto LABEL_20;
    }
    StreamHelper::DeleteStreamProperty(v25, (LPCWSTR)v22, v24);
    if ( v11 )
      break;
LABEL_14:
    if ( v22 )
      LocalFree(v22);
    v5 = a3;
  }
  v18 = *((_DWORD *)a5 + 6 * i);
  hMem = 0;
  v19 = StreamHelper::BuildStreamPropertyFilePath(v25, a2, a3, v18, v24, 0, (unsigned __int16 **)&hMem);
  v13 = v19;
  if ( v19 >= 0 )
  {
    USDeleteFileEx((unsigned __int16 *)hMem);
    if ( hMem )
      LocalFree(hMem);
    goto LABEL_14;
  }
  Log_UnistoreHREvent_0(
    (unsigned int)v19,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
    3188);
  if ( hMem )
    LocalFree(hMem);
LABEL_20:
  if ( v22 )
    LocalFree(v22);
  return v13;
}

```

## disassembly

```asm
0x1800160b0  push    rbp
0x1800160b2  push    rsi
0x1800160b3  push    rdi
0x1800160b4  push    r12
0x1800160b6  push    r13
0x1800160b8  push    r14
0x1800160ba  push    r15
0x1800160bc  lea     rbp, [rsp-180h]
0x1800160c4  sub     rsp, 280h
0x1800160cb  mov     rax, cs:__security_cookie
0x1800160d2  xor     rax, rsp
0x1800160d5  mov     [rbp+1B0h+var_40], rax
0x1800160dc  mov     r14, [rbp+1B0h+arg_20]
0x1800160e3  mov     esi, r8d
0x1800160e6  mov     [rsp+2B0h+var_270], r8d
0x1800160eb  mov     r15d, edx
0x1800160ee  mov     [rsp+2B0h+var_258], 0
0x1800160f7  mov     rdi, rcx
0x1800160fa  test    rcx, rcx
0x1800160fd  jnz     loc_18001634A
0x180016103  mov     r9d, 0C50h
0x180016109  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180016110  xor     edx, edx
0x180016112  mov     ecx, 80070057h
0x180016117  call    Log_UnistoreHREvent_0
0x18001611c  mov     eax, 80070057h
0x180016121  mov     rcx, [rbp+1B0h+var_40]
0x180016128  xor     rcx, rsp; StackCookie
0x18001612b  call    __security_check_cookie
0x180016130  add     rsp, 280h
0x180016137  pop     r15
0x180016139  pop     r14
0x18001613b  pop     r13
0x18001613d  pop     r12
0x18001613f  pop     rdi
0x180016140  pop     rsi
0x180016141  pop     rbp
0x180016142  retn
0x180016143  mov     rax, [rdi]
0x180016146  mov     rcx, rdi
0x180016149  mov     rax, [rax+70h]
0x18001614d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016152  mov     r13d, eax
0x180016155  test    eax, eax
0x180016157  jz      short loc_180016190
0x180016159  mov     rcx, [rdi]
0x18001615c  lea     rdx, [rsp+2B0h+var_258]
0x180016161  mov     rax, [rcx+80h]
0x180016168  mov     rcx, rdi
0x18001616b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016170  mov     esi, eax
0x180016172  test    eax, eax
0x180016174  js      loc_180016308
0x18001617a  mov     rax, [rdi]
0x18001617d  mov     rcx, rdi
0x180016180  mov     rax, [rax+98h]
0x180016187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001618c  mov     esi, [rsp+2B0h+var_270]
0x180016190  lea     rcx, [rsp+2B0h+var_250]; unsigned __int16 *
0x180016195  call    ?GetDefaultStreamRootPath@StreamHelper@@SAJPEAGK@Z; StreamHelper::GetDefaultStreamRootPath(ushort *,ulong)
0x18001619a  mov     edi, eax
0x18001619c  test    eax, eax
0x18001619e  js      loc_1800162D9
0x1800161a4  xor     edi, edi
0x1800161a6  cmp     edi, 1
0x1800161a9  jnb     loc_180016301
0x1800161af  lea     rax, [rsp+2B0h+var_268]
0x1800161b4  mov     [rsp+2B0h+var_268], 0
0x1800161bd  mov     [rsp+2B0h+var_280], rax; unsigned __int16 **
0x1800161c2  lea     r12, [rdi+rdi*2]
0x1800161c6  mov     r9d, [r14+r12*8]; unsigned int
0x1800161ca  lea     rcx, [rsp+2B0h+var_250]; unsigned __int16 *
0x1800161cf  mov     [rsp+2B0h+var_288], 0; int
0x1800161d7  mov     r8d, esi; unsigned int
0x1800161da  mov     edx, r15d; unsigned int
0x1800161dd  mov     [rsp+2B0h+var_290], 0; unsigned __int16 *
0x1800161e6  call    ?BuildStreamPropertyFilePath@StreamHelper@@SAJPEBGKKK0HPEAPEAG@Z; StreamHelper::BuildStreamPropertyFilePath(ushort const *,ulong,ulong,ulong,ushort const *,int,ushort * *)
0x1800161eb  mov     esi, eax
0x1800161ed  test    eax, eax
0x1800161ef  js      loc_1800162AF
0x1800161f5  mov     r8, [rsp+2B0h+var_258]; unsigned __int16 *
0x1800161fa  lea     rcx, [rsp+2B0h+var_250]; unsigned __int16 *
0x1800161ff  mov     rdx, [rsp+2B0h+var_268]; lpExistingFileName
0x180016204  call    ?DeleteStreamProperty@StreamHelper@@SAJPEBG00@Z; StreamHelper::DeleteStreamProperty(ushort const *,ushort const *,ushort const *)
0x180016209  test    r13d, r13d
0x18001620c  jz      short loc_180016269
0x18001620e  mov     rax, [rsp+2B0h+var_258]
0x180016213  lea     rcx, [rsp+2B0h+hMem]
0x180016218  mov     r9d, [r14+r12*8]; unsigned int
0x18001621c  mov     edx, r15d; unsigned int
0x18001621f  mov     r8d, [rsp+2B0h+var_270]; unsigned int
0x180016224  mov     [rsp+2B0h+var_280], rcx; unsigned __int16 **
0x180016229  lea     rcx, [rsp+2B0h+var_250]; unsigned __int16 *
0x18001622e  mov     [rsp+2B0h+var_288], 0; int
0x180016236  mov     [rsp+2B0h+var_290], rax; unsigned __int16 *
0x18001623b  mov     [rsp+2B0h+hMem], 0
0x180016244  call    ?BuildStreamPropertyFilePath@StreamHelper@@SAJPEBGKKK0HPEAPEAG@Z; StreamHelper::BuildStreamPropertyFilePath(ushort const *,ulong,ulong,ulong,ushort const *,int,ushort * *)
0x180016249  mov     esi, eax
0x18001624b  test    eax, eax
0x18001624d  js      short loc_180016284
0x18001624f  mov     rcx, [rsp+2B0h+hMem]; unsigned __int16 *
0x180016254  call    USDeleteFileEx
0x180016259  mov     rcx, [rsp+2B0h+hMem]; hMem
0x18001625e  test    rcx, rcx
0x180016261  jz      short loc_180016269
0x180016263  call    cs:__imp_LocalFree
0x180016269  mov     rcx, [rsp+2B0h+var_268]; hMem
0x18001626e  test    rcx, rcx
0x180016271  jz      short loc_180016279
0x180016273  call    cs:__imp_LocalFree
0x180016279  mov     esi, [rsp+2B0h+var_270]
0x18001627d  inc     edi
0x18001627f  jmp     loc_1800161A6
0x180016284  mov     r9d, 0C74h
0x18001628a  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180016291  mov     edx, 1
0x180016296  mov     ecx, esi
0x180016298  call    Log_UnistoreHREvent_0
0x18001629d  mov     rcx, [rsp+2B0h+hMem]; hMem
0x1800162a2  test    rcx, rcx
0x1800162a5  jz      short loc_1800162C8
0x1800162a7  call    cs:__imp_LocalFree
0x1800162ad  jmp     short loc_1800162C8
0x1800162af  mov     r9d, 0C66h
0x1800162b5  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800162bc  mov     edx, 1
0x1800162c1  mov     ecx, esi
0x1800162c3  call    Log_UnistoreHREvent_0
0x1800162c8  mov     rcx, [rsp+2B0h+var_268]; hMem
0x1800162cd  test    rcx, rcx
0x1800162d0  jnz     short loc_1800162F9
0x1800162d2  mov     eax, esi
0x1800162d4  jmp     loc_180016121
0x1800162d9  mov     r9d, 0C5Fh
0x1800162df  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800162e6  mov     edx, 1
0x1800162eb  mov     ecx, edi
0x1800162ed  call    Log_UnistoreHREvent_0
0x1800162f2  mov     eax, edi
0x1800162f4  jmp     loc_180016121
0x1800162f9  call    cs:__imp_LocalFree
0x1800162ff  jmp     short loc_1800162D2
0x180016301  xor     eax, eax
0x180016303  jmp     loc_180016121
0x180016308  mov     r9d, 0C58h
0x18001630e  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180016315  mov     edx, 1
0x18001631a  mov     ecx, esi
0x18001631c  call    Log_UnistoreHREvent_0
0x180016321  jmp     short loc_1800162D2
0x180016323  mov     ecx, r15d; unsigned int
0x180016326  call    ?IsFileStreamSupportedInTable@@YAHK@Z; IsFileStreamSupportedInTable(ulong)
0x18001632b  test    eax, eax
0x18001632d  jnz     loc_180016143
0x180016333  mov     r8d, 0C52h
0x180016339  lea     rdx, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180016340  call    Log_AssertionEvent
0x180016345  jmp     loc_180016143
0x18001634a  test    r14, r14
0x18001634d  jz      loc_180016103
0x180016353  jmp     short loc_180016323
```
