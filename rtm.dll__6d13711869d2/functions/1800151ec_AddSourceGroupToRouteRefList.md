# AddSourceGroupToRouteRefList

- ea: `0x1800151ec`
- end: `0x1800155f3`
- name: `AddSourceGroupToRouteRefList`
- size: `1031`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180018070`

## callees

- `0x180003f10`
- `0x18000aa60`
- `0x180014d2c`
- `0x180015178`
- `0x1800151ec`
- `0x1800157ec`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18001525d`
- `KERNEL32!HeapAlloc` at `0x18001533d`
- `KERNEL32!HeapAlloc` at `0x18001525d`
- `KERNEL32!HeapAlloc` at `0x18001533d`
- `KERNEL32!HeapFree` at `0x18001548d`
- `KERNEL32!HeapFree` at `0x1800154f4`
- `KERNEL32!HeapFree` at `0x18001548d`
- `KERNEL32!HeapFree` at `0x1800154f4`

## string_xrefs

- `0x180015449`: `Reference already exists for source %x`

## pseudocode

```c
int __fastcall AddSourceGroupToRouteRefList(
        unsigned int a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5,
        RTM_DEST_HANDLE *a6)
{
  int v6; // esi
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  int v11; // r15d
  DWORD OpaqueInformationPointer; // eax
  _QWORD *v13; // r14
  __int64 v14; // rdi
  __int64 v15; // r8
  const wchar_t *v16; // rdx
  __int64 v17; // r14
  int v18; // r8d
  _QWORD *v19; // rax
  PVOID OpaqueInfoPointer; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h]
  int v24; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v25[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v6 = 0;
  OpaqueInfoPointer = 0;
  v23 = 0;
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v9 = HeapAlloc(hHeap, 0, 0x28u);
  v10 = v9;
  if ( !v9 )
  {
    if ( qword_18002B8A8 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(&v24, L"Failed to allocate %d bytes", 40);
LABEL_45:
      LODWORD(v9) = ((__int64 (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(
                      gMgmEtwContext,
                      qword_18002B8A8,
                      &v24);
      return (int)v9;
    }
    return (int)v9;
  }
  *((_DWORD *)v9 + 4) = a3;
  v11 = 0;
  *((_DWORD *)v9 + 6) = a1;
  *((_DWORD *)v9 + 7) = -1;
  *((_DWORD *)v9 + 5) = 0;
  v9[4] = a5;
  v9[1] = v9;
  *v9 = v9;
  if ( (unsigned __int64)*a6 == 0x7754DF32 || *(_WORD *)(((unsigned __int64)*a6 ^ 0x7754DF32) + 0x6C) == 1 )
  {
    if ( !qword_18002B8A8 )
      goto LABEL_34;
    v15 = 6;
    v16 = L"Failed to lock dest %x";
    goto LABEL_32;
  }
  AcquireWriteLock(((unsigned __int64)*a6 ^ 0x7754DF32) + 32);
  v6 = 1;
  OpaqueInformationPointer = RtmGetOpaqueInformationPointer(g_hRtmHandle, *a6, &OpaqueInfoPointer);
  if ( !OpaqueInformationPointer )
  {
    v13 = OpaqueInfoPointer;
    v14 = *(_QWORD *)OpaqueInfoPointer;
    if ( *(_QWORD *)OpaqueInfoPointer )
    {
      v17 = v14 + 16;
      AcquireWriteLock(v14 + 16);
      if ( (unsigned __int64)*a6 == 0x7754DF32 || *(_WORD *)(((unsigned __int64)*a6 ^ 0x7754DF32) + 0x6C) == 1 )
      {
        if ( qword_18002B8A8 )
        {
          LOWORD(v24) = 0;
          FormatRRASErrorString(&v24, L"Failed to release dest %x", 6);
          ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v24);
        }
      }
      else
      {
        ReleaseWriteLock(((unsigned __int64)*a6 ^ 0x7754DF32) + 32);
      }
      if ( (unsigned int)FindRefEntry(v14, a1, v18, a3) )
      {
        if ( qword_18002B8A8 )
        {
          LOWORD(v24) = 0;
          FormatRRASErrorString(&v24, L"Reference already exists for source %x", a1);
          ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v24);
        }
        HeapFree(hHeap, 0, v10);
      }
      else
      {
        if ( v23 )
          v14 = v23;
        v19 = *(_QWORD **)(v14 + 8);
        if ( *v19 != v14 )
          __fastfail(3u);
        *v10 = v14;
        v10[1] = v19;
        *v19 = v10;
        *(_QWORD *)(v14 + 8) = v10;
      }
      v6 = 0;
      LODWORD(v9) = ReleaseWriteLock(v17);
    }
    else
    {
      v9 = HeapAlloc(hHeap, 0, 0x20u);
      if ( !v9 )
      {
        if ( !qword_18002B8A8 )
          goto LABEL_34;
        v15 = 8;
        v16 = L"AddSourceGroupToRouteRefList : Failed to allocate route ref list %x";
LABEL_32:
        LOWORD(v24) = 0;
        FormatRRASErrorString(&v24, v16, v15);
        goto LABEL_33;
      }
      v9[2] = 0;
      *((_DWORD *)v9 + 6) = 305419896;
      *v10 = v9;
      v10[1] = v9;
      *v9 = v10;
      v9[1] = v10;
      *v13 = v9;
    }
    v11 = v6;
    goto LABEL_35;
  }
  if ( qword_18002B8A8 )
  {
    LOWORD(v24) = 0;
    FormatRRASErrorString(&v24, L"Failed to retrieve opaque pointer %x", OpaqueInformationPointer);
LABEL_33:
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v24);
  }
LABEL_34:
  LODWORD(v9) = HeapFree(hHeap, 0, v10);
LABEL_35:
  if ( v6 )
  {
    if ( (unsigned __int64)*a6 == 0x7754DF32
      || (LODWORD(v9) = 1, *(_WORD *)(((unsigned __int64)*a6 ^ 0x7754DF32) + 0x6C) == 1) )
    {
      if ( qword_18002B8A8 )
      {
        LOWORD(v24) = 0;
        FormatRRASErrorString(&v24, L"Failed to release dest %x", 6);
        LODWORD(v9) = ((__int64 (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(
                        gMgmEtwContext,
                        qword_18002B8A8,
                        &v24);
      }
    }
    else
    {
      LODWORD(v9) = ReleaseWriteLock(((unsigned __int64)*a6 ^ 0x7754DF32) + 32);
    }
  }
  if ( v11 )
  {
    LODWORD(v9) = RtmMarkDestForChangeNotification(g_hRtmHandle, g_hNotificationHandle, *a6, 1);
    if ( (_DWORD)v9 )
    {
      if ( qword_18002B8A8 )
      {
        LOWORD(v24) = 0;
        FormatRRASErrorString(&v24, L"Failed to mark destination %x:", (unsigned int)v9);
        goto LABEL_45;
      }
    }
  }
  return (int)v9;
}

```

## disassembly

```asm
0x1800151ec  push    rbp
0x1800151ee  push    rbx
0x1800151ef  push    rsi
0x1800151f0  push    rdi
0x1800151f1  push    r12
0x1800151f3  push    r13
0x1800151f5  push    r14
0x1800151f7  push    r15
0x1800151f9  lea     rbp, [rsp-768h]
0x180015201  sub     rsp, 868h
0x180015208  mov     rax, cs:__security_cookie
0x18001520f  xor     rax, rsp
0x180015212  mov     [rbp+7A0h+var_50], rax
0x180015219  mov     r12, [rbp+7A0h+arg_28]
0x180015220  xor     esi, esi
0x180015222  mov     edi, r8d
0x180015225  mov     [rsp+8A0h+var_870], r8d
0x18001522a  mov     r13d, ecx
0x18001522d  mov     [rsp+8A0h+OpaqueInfoPointer], rsi
0x180015232  mov     r8d, 7FCh; Size
0x180015238  mov     [rsp+8A0h+var_860], rsi
0x18001523d  lea     rcx, [rsp+8A0h+var_84C]; void *
0x180015242  mov     [rsp+8A0h+var_850], esi
0x180015246  xor     edx, edx; Val
0x180015248  call    memset_0
0x18001524d  mov     rcx, cs:hHeap; hHeap
0x180015254  lea     r14d, [rsi+28h]
0x180015258  mov     r8d, r14d; dwBytes
0x18001525b  xor     edx, edx; dwFlags
0x18001525d  call    cs:__imp_HeapAlloc
0x180015263  mov     rbx, rax
0x180015266  test    rax, rax
0x180015269  jnz     short loc_180015296
0x18001526b  cmp     cs:qword_18002B8A8, rsi
0x180015272  jz      loc_1800155D0
0x180015278  mov     r8d, r14d
0x18001527b  mov     word ptr [rsp+8A0h+var_850], si
0x180015280  lea     rdx, aFailedToAlloca_1; "Failed to allocate %d bytes"
0x180015287  lea     rcx, [rsp+8A0h+var_850]
0x18001528c  call    FormatRRASErrorString
0x180015291  jmp     loc_1800155B1
0x180015296  mov     [rax+10h], edi
0x180015299  mov     r15d, esi
0x18001529c  mov     [rax+18h], r13d
0x1800152a0  mov     edi, 1
0x1800152a5  mov     dword ptr [rax+1Ch], 0FFFFFFFFh
0x1800152ac  mov     [rax+14h], esi
0x1800152af  mov     rax, [rbp+7A0h+arg_20]
0x1800152b6  mov     [rbx+20h], rax
0x1800152ba  mov     [rbx+8], rbx
0x1800152be  mov     [rbx], rbx
0x1800152c1  mov     rcx, [r12]
0x1800152c5  xor     rcx, 7754DF32h
0x1800152cc  jz      loc_1800154A2
0x1800152d2  cmp     [rcx+6Ch], di
0x1800152d6  jz      loc_1800154A2
0x1800152dc  add     rcx, 20h ; ' '
0x1800152e0  call    AcquireWriteLock
0x1800152e5  mov     rdx, [r12]; DestHandle
0x1800152e9  lea     r8, [rsp+8A0h+OpaqueInfoPointer]; OpaqueInfoPointer
0x1800152ee  mov     rcx, cs:g_hRtmHandle; RtmRegHandle
0x1800152f5  mov     esi, edi
0x1800152f7  call    RtmGetOpaqueInformationPointer
0x1800152fc  test    eax, eax
0x1800152fe  jz      short loc_180015323
0x180015300  cmp     cs:qword_18002B8A8, r15
0x180015307  jz      loc_1800154E8
0x18001530d  xor     ecx, ecx
0x18001530f  lea     rdx, aFailedToRetrie; "Failed to retrieve opaque pointer %x"
0x180015316  mov     word ptr [rsp+8A0h+var_850], cx
0x18001531b  mov     r8d, eax
0x18001531e  jmp     loc_1800154BF
0x180015323  mov     r14, [rsp+8A0h+OpaqueInfoPointer]
0x180015328  mov     rdi, [r14]
0x18001532b  test    rdi, rdi
0x18001532e  jnz     short loc_180015386
0x180015330  mov     rcx, cs:hHeap; hHeap
0x180015337  lea     r8d, [rdi+20h]; dwBytes
0x18001533b  xor     edx, edx; dwFlags
0x18001533d  call    cs:__imp_HeapAlloc
0x180015343  test    rax, rax
0x180015346  jnz     short loc_180015365
0x180015348  cmp     cs:qword_18002B8A8, r15
0x18001534f  jz      loc_1800154E8
0x180015355  lea     r8d, [rdi+8]
0x180015359  lea     rdx, aAddsourcegroup; "AddSourceGroupToRouteRefList : Failed t"...
0x180015360  jmp     loc_1800154B8
0x180015365  mov     [rax+10h], r15
0x180015369  mov     dword ptr [rax+18h], 12345678h
0x180015370  mov     [rbx], rax
0x180015373  mov     [rbx+8], rax
0x180015377  mov     [rax], rbx
0x18001537a  mov     [rax+8], rbx
0x18001537e  mov     [r14], rax
0x180015381  jmp     loc_18001549D
0x180015386  lea     r14, [rdi+10h]
0x18001538a  mov     rcx, r14
0x18001538d  call    AcquireWriteLock
0x180015392  mov     rcx, [r12]
0x180015396  xor     rcx, 7754DF32h
0x18001539d  jz      short loc_1800153B0
0x18001539f  cmp     [rcx+6Ch], si
0x1800153a3  jz      short loc_1800153B0
0x1800153a5  add     rcx, 20h ; ' '
0x1800153a9  call    ReleaseWriteLock
0x1800153ae  jmp     short loc_1800153F4
0x1800153b0  cmp     cs:qword_18002B8A8, r15
0x1800153b7  jz      short loc_1800153F4
0x1800153b9  xor     eax, eax
0x1800153bb  lea     rdx, aFailedToReleas_1; "Failed to release dest %x"
0x1800153c2  lea     rcx, [rsp+8A0h+var_850]
0x1800153c7  mov     word ptr [rsp+8A0h+var_850], ax
0x1800153cc  lea     r8d, [rax+6]
0x1800153d0  call    FormatRRASErrorString
0x1800153d5  mov     rdx, cs:qword_18002B8A8
0x1800153dc  lea     r8, [rsp+8A0h+var_850]
0x1800153e1  mov     rcx, cs:gMgmEtwContext
0x1800153e8  mov     rax, cs:gMgmTemplateFunc
0x1800153ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153f4  mov     r9d, [rsp+8A0h+var_870]
0x1800153f9  lea     rax, [rsp+8A0h+var_860]
0x1800153fe  mov     edx, r13d
0x180015401  mov     [rsp+8A0h+var_878], rax
0x180015406  mov     rcx, rdi
0x180015409  call    FindRefEntry
0x18001540e  test    eax, eax
0x180015410  jnz     short loc_18001543E
0x180015412  mov     rax, [rsp+8A0h+var_860]
0x180015417  test    rax, rax
0x18001541a  cmovnz  rdi, rax
0x18001541e  mov     rax, [rdi+8]
0x180015422  cmp     [rax], rdi
0x180015425  jz      short loc_18001542E
0x180015427  mov     ecx, 3
0x18001542c  int     29h; Win8: RtlFailFast(ecx)
0x18001542e  mov     [rbx], rdi
0x180015431  mov     [rbx+8], rax
0x180015435  mov     [rax], rbx
0x180015438  mov     [rdi+8], rbx
0x18001543c  jmp     short loc_180015493
0x18001543e  cmp     cs:qword_18002B8A8, r15
0x180015445  jz      short loc_180015481
0x180015447  xor     eax, eax
0x180015449  lea     rdx, aReferenceAlrea; "Reference already exists for source %x"
0x180015450  mov     r8d, r13d
0x180015453  mov     word ptr [rsp+8A0h+var_850], ax
0x180015458  lea     rcx, [rsp+8A0h+var_850]
0x18001545d  call    FormatRRASErrorString
0x180015462  mov     rdx, cs:qword_18002B8A8
0x180015469  lea     r8, [rsp+8A0h+var_850]
0x18001546e  mov     rcx, cs:gMgmEtwContext
0x180015475  mov     rax, cs:gMgmTemplateFunc
0x18001547c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015481  mov     rcx, cs:hHeap; hHeap
0x180015488  mov     r8, rbx; lpMem
0x18001548b  xor     edx, edx; dwFlags
0x18001548d  call    cs:__imp_HeapFree
0x180015493  xor     esi, esi
0x180015495  mov     rcx, r14
0x180015498  call    ReleaseWriteLock
0x18001549d  mov     r15d, esi
0x1800154a0  jmp     short loc_1800154FA
0x1800154a2  cmp     cs:qword_18002B8A8, rsi
0x1800154a9  jz      short loc_1800154E8
0x1800154ab  mov     r8d, 6
0x1800154b1  lea     rdx, aFailedToLockDe; "Failed to lock dest %x"
0x1800154b8  xor     eax, eax
0x1800154ba  mov     word ptr [rsp+8A0h+var_850], ax
0x1800154bf  lea     rcx, [rsp+8A0h+var_850]
0x1800154c4  call    FormatRRASErrorString
0x1800154c9  mov     rdx, cs:qword_18002B8A8
0x1800154d0  lea     r8, [rsp+8A0h+var_850]
0x1800154d5  mov     rcx, cs:gMgmEtwContext
0x1800154dc  mov     rax, cs:gMgmTemplateFunc
0x1800154e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154e8  mov     rcx, cs:hHeap; hHeap
0x1800154ef  mov     r8, rbx; lpMem
0x1800154f2  xor     edx, edx; dwFlags
0x1800154f4  call    cs:__imp_HeapFree
0x1800154fa  test    esi, esi
0x1800154fc  jz      short loc_180015566
0x1800154fe  mov     rcx, [r12]
0x180015502  xor     rcx, 7754DF32h
0x180015509  jz      short loc_180015521
0x18001550b  mov     eax, 1
0x180015510  cmp     [rcx+6Ch], ax
0x180015514  jz      short loc_180015521
0x180015516  add     rcx, 20h ; ' '
0x18001551a  call    ReleaseWriteLock
0x18001551f  jmp     short loc_180015566
0x180015521  cmp     cs:qword_18002B8A8, 0
0x180015529  jz      short loc_180015566
0x18001552b  xor     eax, eax
0x18001552d  lea     rdx, aFailedToReleas_1; "Failed to release dest %x"
0x180015534  lea     rcx, [rsp+8A0h+var_850]
0x180015539  mov     word ptr [rsp+8A0h+var_850], ax
0x18001553e  lea     r8d, [rax+6]
0x180015542  call    FormatRRASErrorString
0x180015547  mov     rdx, cs:qword_18002B8A8
0x18001554e  lea     r8, [rsp+8A0h+var_850]
0x180015553  mov     rcx, cs:gMgmEtwContext
0x18001555a  mov     rax, cs:gMgmTemplateFunc
0x180015561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015566  test    r15d, r15d
0x180015569  jz      short loc_1800155D0
0x18001556b  mov     r8, [r12]; DestHandle
0x18001556f  mov     r9d, 1; MarkDest
0x180015575  mov     rdx, cs:g_hNotificationHandle; NotifyHandle
0x18001557c  mov     rcx, cs:g_hRtmHandle; RtmRegHandle
0x180015583  call    RtmMarkDestForChangeNotification
0x180015588  test    eax, eax
0x18001558a  jz      short loc_1800155D0
0x18001558c  cmp     cs:qword_18002B8A8, 0
0x180015594  jz      short loc_1800155D0
0x180015596  xor     ecx, ecx
0x180015598  lea     rdx, aFailedToMarkDe; "Failed to mark destination %x:"
0x18001559f  mov     word ptr [rsp+8A0h+var_850], cx
0x1800155a4  mov     r8d, eax
0x1800155a7  lea     rcx, [rsp+8A0h+var_850]
0x1800155ac  call    FormatRRASErrorString
0x1800155b1  mov     rdx, cs:qword_18002B8A8
0x1800155b8  lea     r8, [rsp+8A0h+var_850]
0x1800155bd  mov     rcx, cs:gMgmEtwContext
0x1800155c4  mov     rax, cs:gMgmTemplateFunc
0x1800155cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155d0  mov     rcx, [rbp+7A0h+var_50]
0x1800155d7  xor     rcx, rsp; StackCookie
0x1800155da  call    __security_check_cookie
0x1800155df  add     rsp, 868h
0x1800155e6  pop     r15
0x1800155e8  pop     r14
0x1800155ea  pop     r13
0x1800155ec  pop     r12
0x1800155ee  pop     rdi
0x1800155ef  pop     rsi
0x1800155f0  pop     rbx
0x1800155f1  pop     rbp
0x1800155f2  retn
```
