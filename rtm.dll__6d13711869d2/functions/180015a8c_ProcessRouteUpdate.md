# ProcessRouteUpdate

- ea: `0x180015a8c`
- end: `0x180015f4e`
- name: `ProcessRouteUpdate`
- size: `1218`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x1800167d0`

## callees

- `0x180003f10`
- `0x1800071a0`
- `0x180007350`
- `0x18000aa60`
- `0x180014d2c`
- `0x180015178`
- `0x1800155fc`
- `0x180015a8c`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180015b0c`
- `KERNEL32!HeapAlloc` at `0x180015b0c`
- `KERNEL32!HeapFree` at `0x180015d8a`
- `KERNEL32!HeapFree` at `0x180015ef6`
- `KERNEL32!HeapFree` at `0x180015d8a`
- `KERNEL32!HeapFree` at `0x180015ef6`

## pseudocode

```c
__int64 __fastcall ProcessRouteUpdate(RTM_DEST_HANDLE *a1)
{
  int v2; // r14d
  unsigned __int64 v3; // rcx
  unsigned int v4; // ebx
  struct _RTM_ROUTE_INFO *v5; // r12
  unsigned int v6; // ebx
  int v7; // r13d
  DWORD OpaqueInformationPointer; // eax
  __int64 v9; // r8
  __int64 v10; // rdi
  DWORD RouteInfo; // eax
  __int64 v12; // r8
  const wchar_t *v13; // rdx
  __int64 *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rbx
  __int64 **v17; // rax
  DWORD v18; // eax
  __int64 v19; // rcx
  DWORD v20; // eax
  _QWORD *v21; // r14
  _QWORD *v22; // rbx
  __int64 v23; // rcx
  DWORD v24; // eax
  PVOID OpaqueInfoPointer[2]; // [rsp+20h] [rbp-E0h] BYREF
  int v27; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v28[2044]; // [rsp+34h] [rbp-CCh] BYREF

  v2 = 0;
  OpaqueInfoPointer[0] = 0;
  v27 = 0;
  memset_0(v28, 0, sizeof(v28));
  v3 = 8LL * (g_rrpRtmProfile.MaxNextHopsInRoute - 1);
  if ( v3 <= 0xFFFFFFFF )
  {
    v4 = v3 + 64;
    if ( (int)v3 + 64 >= (unsigned int)v3 )
    {
      v5 = (struct _RTM_ROUTE_INFO *)HeapAlloc(hHeap, 0, v4);
      if ( !v5 )
      {
        if ( qword_18002B8A8 )
        {
          LOWORD(v27) = 0;
          FormatRRASErrorString(&v27, L"Failed to allocate route info, size : %x", v4);
          ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v27);
        }
        return 8;
      }
      if ( (unsigned __int64)*a1 != 0x7754DF32 && *(_WORD *)(((unsigned __int64)*a1 ^ 0x7754DF32) + 0x6C) != 1 )
      {
        v7 = 0;
        AcquireWriteLock((_QWORD *)(((unsigned __int64)*a1 ^ 0x7754DF32) + 32));
        OpaqueInformationPointer = RtmGetOpaqueInformationPointer(g_hRtmHandle, *a1, OpaqueInfoPointer);
        if ( OpaqueInformationPointer )
        {
          if ( !qword_18002B8A8 )
            goto LABEL_45;
          v9 = OpaqueInformationPointer;
          goto LABEL_44;
        }
        v10 = *(_QWORD *)OpaqueInfoPointer[0];
        if ( !*(_QWORD *)OpaqueInfoPointer[0] )
        {
          v7 = 1;
          goto LABEL_45;
        }
        AcquireWriteLock((_QWORD *)(v10 + 16));
        if ( (unsigned __int64)*a1 != 0x7754DF32 && *(_WORD *)(((unsigned __int64)*a1 ^ 0x7754DF32) + 0x6C) != 1 )
        {
          ReleaseWriteLock(((unsigned __int64)*a1 ^ 0x7754DF32) + 32);
          RouteInfo = RtmGetRouteInfo(g_hRtmHandle, a1[7], v5, 0);
          v6 = RouteInfo;
          if ( RouteInfo )
          {
            if ( qword_18002B8A8 )
            {
              v12 = RouteInfo;
              v13 = L"Failed route info : %x";
LABEL_57:
              LOWORD(v27) = 0;
              FormatRRASErrorString(&v27, v13, v12);
              ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v27);
              goto LABEL_58;
            }
            goto LABEL_58;
          }
          v14 = *(__int64 **)v10;
          if ( *(_QWORD *)v10 != v10 )
          {
            do
            {
              if ( v5->NextHopsList.NumNextHops )
              {
                v15 = 0;
                while ( (RTM_NEXTHOP_HANDLE)v14[4] != v5->NextHopsList.NextHops[v15] )
                {
                  v2 = 0;
                  v15 = (unsigned int)(v15 + 1);
                  if ( (unsigned int)v15 >= v5->NextHopsList.NumNextHops )
                  {
                    v16 = *v14;
                    goto LABEL_27;
                  }
                }
                v16 = *v14;
                v2 = 1;
              }
              else
              {
                v16 = *v14;
                if ( !v2 )
                {
LABEL_27:
                  if ( *(__int64 **)(v16 + 8) != v14 || (v17 = (__int64 **)v14[1], *v17 != v14) )
                    __fastfail(3u);
                  *v17 = (__int64 *)v16;
                  *(_QWORD *)(v16 + 8) = v17;
                  DeleteMfeAndRefs(v14);
                }
              }
              v14 = (__int64 *)v16;
            }
            while ( v16 != v10 );
          }
          v18 = RtmReleaseRouteInfo(g_hRtmHandle, v5);
          v6 = v18;
          if ( v18 && qword_18002B8A8 )
          {
            LOWORD(v27) = 0;
            FormatRRASErrorString(&v27, L"Failed to release route info : %x", v18);
            ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v27);
          }
          v19 = v10 + 16;
          if ( *(_QWORD *)v10 != v10 )
          {
            ReleaseWriteLock(v19);
            goto LABEL_58;
          }
          ReleaseWriteLock(v19);
          if ( (unsigned __int64)*a1 != 0x7754DF32 && *(_WORD *)(((unsigned __int64)*a1 ^ 0x7754DF32) + 0x6C) != 1 )
          {
            AcquireWriteLock((_QWORD *)(((unsigned __int64)*a1 ^ 0x7754DF32) + 32));
            v20 = RtmGetOpaqueInformationPointer(g_hRtmHandle, *a1, OpaqueInfoPointer);
            v9 = v20;
            if ( !v20 )
            {
              v21 = OpaqueInfoPointer[0];
              v22 = *(_QWORD **)OpaqueInfoPointer[0];
              if ( *(_QWORD *)OpaqueInfoPointer[0] )
              {
                AcquireWriteLock(v22 + 2);
                v23 = (__int64)(v22 + 2);
                if ( (_QWORD *)*v22 == v22 )
                {
                  *v21 = 0;
                  ReleaseWriteLock(v23);
                  HeapFree(hHeap, 0, v22);
                  v7 = 1;
                }
                else
                {
                  ReleaseWriteLock(v23);
                }
                goto LABEL_45;
              }
            }
            if ( !qword_18002B8A8 )
            {
LABEL_45:
              if ( (unsigned __int64)*a1 == 0x7754DF32 || *(_WORD *)(((unsigned __int64)*a1 ^ 0x7754DF32) + 0x6C) == 1 )
              {
                v6 = 6;
                if ( qword_18002B8A8 )
                {
                  LOWORD(v27) = 0;
                  FormatRRASErrorString(&v27, L"Failed to lock dest : %x", 6);
                  ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(
                    gMgmEtwContext,
                    qword_18002B8A8,
                    &v27);
                }
              }
              else
              {
                ReleaseWriteLock(((unsigned __int64)*a1 ^ 0x7754DF32) + 32);
                v6 = 0;
              }
              if ( !v7 )
                goto LABEL_58;
              v24 = RtmMarkDestForChangeNotification(g_hRtmHandle, g_hNotificationHandle, *a1, 0);
              v6 = v24;
              if ( !v24 || !qword_18002B8A8 )
                goto LABEL_58;
              v12 = v24;
              v13 = L"Failed to unmark DEST: %x";
              goto LABEL_57;
            }
LABEL_44:
            LOWORD(v27) = 0;
            FormatRRASErrorString(&v27, L"Failed to get opaque ptr : %x", v9);
            ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v27);
            goto LABEL_45;
          }
        }
      }
      v6 = 6;
      if ( qword_18002B8A8 )
      {
        v12 = 6;
        v13 = L"Failed to lock dest : %x";
        goto LABEL_57;
      }
LABEL_58:
      HeapFree(hHeap, 0, v5);
      return v6;
    }
  }
  v6 = 534;
  if ( qword_18002B8A8 )
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(
      gMgmEtwContext,
      qword_18002B8A8,
      L"Arithmatic Overflow Error. Failed to allocate route info ");
  return v6;
}

```

## disassembly

```asm
0x180015a8c  push    rbp
0x180015a8e  push    rbx
0x180015a8f  push    rsi
0x180015a90  push    rdi
0x180015a91  push    r12
0x180015a93  push    r13
0x180015a95  push    r14
0x180015a97  push    r15
0x180015a99  lea     rbp, [rsp-748h]
0x180015aa1  sub     rsp, 848h
0x180015aa8  mov     rax, cs:__security_cookie
0x180015aaf  xor     rax, rsp
0x180015ab2  mov     [rbp+780h+var_50], rax
0x180015ab9  mov     rsi, rcx
0x180015abc  xor     r14d, r14d
0x180015abf  lea     rcx, [rsp+880h+var_84C]; void *
0x180015ac4  mov     [rsp+880h+OpaqueInfoPointer], r14
0x180015ac9  xor     edx, edx; Val
0x180015acb  mov     [rsp+880h+var_850], r14d
0x180015ad0  mov     r8d, 7FCh; Size
0x180015ad6  call    memset_0
0x180015adb  mov     ecx, cs:g_rrpRtmProfile.MaxNextHopsInRoute
0x180015ae1  mov     eax, 0FFFFFFFFh
0x180015ae6  dec     ecx
0x180015ae8  shl     rcx, 3
0x180015aec  cmp     rcx, rax
0x180015aef  ja      loc_180015EFE
0x180015af5  lea     ebx, [rcx+40h]
0x180015af8  cmp     ebx, ecx
0x180015afa  jb      loc_180015EFE
0x180015b00  mov     rcx, cs:hHeap; hHeap
0x180015b07  xor     edx, edx; dwFlags
0x180015b09  mov     r8d, ebx; dwBytes
0x180015b0c  call    cs:__imp_HeapAlloc
0x180015b12  mov     r12, rax
0x180015b15  test    rax, rax
0x180015b18  jnz     short loc_180015B66
0x180015b1a  cmp     cs:qword_18002B8A8, r14
0x180015b21  jz      short loc_180015B5C
0x180015b23  mov     r8d, ebx
0x180015b26  mov     word ptr [rsp+880h+var_850], r14w
0x180015b2c  lea     rdx, aFailedToAlloca_3; "Failed to allocate route info, size : %"...
0x180015b33  lea     rcx, [rsp+880h+var_850]
0x180015b38  call    FormatRRASErrorString
0x180015b3d  mov     rdx, cs:qword_18002B8A8
0x180015b44  lea     r8, [rsp+880h+var_850]
0x180015b49  mov     rcx, cs:gMgmEtwContext
0x180015b50  mov     rax, cs:gMgmTemplateFunc
0x180015b57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b5c  mov     ebx, 8
0x180015b61  jmp     loc_180015F29
0x180015b66  mov     rcx, [rsi]
0x180015b69  xor     rcx, 7754DF32h
0x180015b70  jz      loc_180015EA3
0x180015b76  mov     ebx, 1
0x180015b7b  cmp     [rcx+6Ch], bx
0x180015b7f  jz      loc_180015EA3
0x180015b85  add     rcx, 20h ; ' '
0x180015b89  mov     r13d, r14d
0x180015b8c  call    AcquireWriteLock
0x180015b91  mov     rdx, [rsi]; DestHandle
0x180015b94  lea     r8, [rsp+880h+OpaqueInfoPointer]; OpaqueInfoPointer
0x180015b99  mov     rcx, cs:g_hRtmHandle; RtmRegHandle
0x180015ba0  call    RtmGetOpaqueInformationPointer
0x180015ba5  test    eax, eax
0x180015ba7  jz      short loc_180015BBE
0x180015ba9  cmp     cs:qword_18002B8A8, r14
0x180015bb0  jz      loc_180015DF8
0x180015bb6  mov     r8d, eax
0x180015bb9  jmp     loc_180015DC2
0x180015bbe  mov     rax, [rsp+880h+OpaqueInfoPointer]
0x180015bc3  mov     rdi, [rax]
0x180015bc6  test    rdi, rdi
0x180015bc9  jnz     short loc_180015BD3
0x180015bcb  mov     r13d, ebx
0x180015bce  jmp     loc_180015DF8
0x180015bd3  lea     r15, [rdi+10h]
0x180015bd7  mov     rcx, r15
0x180015bda  call    AcquireWriteLock
0x180015bdf  mov     rcx, [rsi]
0x180015be2  xor     rcx, 7754DF32h
0x180015be9  jz      loc_180015EA3
0x180015bef  cmp     [rcx+6Ch], bx
0x180015bf3  jz      loc_180015EA3
0x180015bf9  add     rcx, 20h ; ' '
0x180015bfd  call    ReleaseWriteLock
0x180015c02  mov     rdx, [rsi+38h]; RouteHandle
0x180015c06  xor     r9d, r9d; DestAddress
0x180015c09  mov     rcx, cs:g_hRtmHandle; RtmRegHandle
0x180015c10  mov     r8, r12; RouteInfo
0x180015c13  call    RtmGetRouteInfo
0x180015c18  mov     ebx, eax
0x180015c1a  test    eax, eax
0x180015c1c  jz      short loc_180015C3A
0x180015c1e  cmp     cs:qword_18002B8A8, r14
0x180015c25  jz      loc_180015EEA
0x180015c2b  mov     r8d, eax
0x180015c2e  lea     rdx, aFailedRouteInf; "Failed route info : %x"
0x180015c35  jmp     loc_180015EBB
0x180015c3a  mov     rcx, [rdi]; lpMem
0x180015c3d  cmp     rcx, rdi
0x180015c40  jz      short loc_180015CA7
0x180015c42  movzx   r8d, word ptr [r12+30h]
0x180015c48  test    r8d, r8d
0x180015c4b  jz      short loc_180015C74
0x180015c4d  mov     r9, [rcx+20h]
0x180015c51  xor     edx, edx
0x180015c53  cmp     r9, [r12+rdx*8+38h]
0x180015c58  jz      short loc_180015C69
0x180015c5a  xor     r14d, r14d
0x180015c5d  inc     edx
0x180015c5f  cmp     edx, r8d
0x180015c62  jb      short loc_180015C53
0x180015c64  mov     rbx, [rcx]
0x180015c67  jmp     short loc_180015C7C
0x180015c69  mov     rbx, [rcx]
0x180015c6c  mov     r14d, 1
0x180015c72  jmp     short loc_180015C9F
0x180015c74  mov     rbx, [rcx]
0x180015c77  test    r14d, r14d
0x180015c7a  jnz     short loc_180015C9F
0x180015c7c  cmp     [rbx+8], rcx
0x180015c80  jnz     loc_180015D9D
0x180015c86  mov     rax, [rcx+8]
0x180015c8a  cmp     [rax], rcx
0x180015c8d  jnz     loc_180015D9D
0x180015c93  mov     [rax], rbx
0x180015c96  mov     [rbx+8], rax
0x180015c9a  call    DeleteMfeAndRefs
0x180015c9f  mov     rcx, rbx
0x180015ca2  cmp     rbx, rdi
0x180015ca5  jnz     short loc_180015C42
0x180015ca7  mov     rcx, cs:g_hRtmHandle; RtmRegHandle
0x180015cae  mov     rdx, r12; RouteInfo
0x180015cb1  call    RtmReleaseRouteInfo
0x180015cb6  xor     r14d, r14d
0x180015cb9  mov     ebx, eax
0x180015cbb  test    eax, eax
0x180015cbd  jz      short loc_180015D01
0x180015cbf  cmp     cs:qword_18002B8A8, r14
0x180015cc6  jz      short loc_180015D01
0x180015cc8  mov     r8d, eax
0x180015ccb  mov     word ptr [rsp+880h+var_850], r14w
0x180015cd1  lea     rdx, aFailedToReleas; "Failed to release route info : %x"
0x180015cd8  lea     rcx, [rsp+880h+var_850]
0x180015cdd  call    FormatRRASErrorString
0x180015ce2  mov     rdx, cs:qword_18002B8A8
0x180015ce9  lea     r8, [rsp+880h+var_850]
0x180015cee  mov     rcx, cs:gMgmEtwContext
0x180015cf5  mov     rax, cs:gMgmTemplateFunc
0x180015cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d01  mov     rcx, r15
0x180015d04  cmp     [rdi], rdi
0x180015d07  jnz     loc_180015E9C
0x180015d0d  call    ReleaseWriteLock
0x180015d12  mov     rcx, [rsi]
0x180015d15  xor     rcx, 7754DF32h
0x180015d1c  jz      loc_180015EA3
0x180015d22  mov     ebx, 1
0x180015d27  cmp     [rcx+6Ch], bx
0x180015d2b  jz      loc_180015EA3
0x180015d31  add     rcx, 20h ; ' '
0x180015d35  call    AcquireWriteLock
0x180015d3a  mov     rdx, [rsi]; DestHandle
0x180015d3d  lea     r8, [rsp+880h+OpaqueInfoPointer]; OpaqueInfoPointer
0x180015d42  mov     rcx, cs:g_hRtmHandle; RtmRegHandle
0x180015d49  call    RtmGetOpaqueInformationPointer
0x180015d4e  mov     r8d, eax
0x180015d51  test    eax, eax
0x180015d53  jnz     short loc_180015DB9
0x180015d55  mov     r14, [rsp+880h+OpaqueInfoPointer]
0x180015d5a  mov     rbx, [r14]
0x180015d5d  test    rbx, rbx
0x180015d60  jz      short loc_180015DB2
0x180015d62  lea     rdi, [rbx+10h]
0x180015d66  mov     rcx, rdi
0x180015d69  call    AcquireWriteLock
0x180015d6e  mov     rcx, rdi
0x180015d71  cmp     [rbx], rbx
0x180015d74  jnz     short loc_180015DA4
0x180015d76  mov     [r14], r13
0x180015d79  call    ReleaseWriteLock
0x180015d7e  mov     rcx, cs:hHeap; hHeap
0x180015d85  mov     r8, rbx; lpMem
0x180015d88  xor     edx, edx; dwFlags
0x180015d8a  call    cs:__imp_HeapFree
0x180015d90  mov     ebx, 1
0x180015d95  xor     r14d, r14d
0x180015d98  mov     r13d, ebx
0x180015d9b  jmp     short loc_180015DF8
0x180015d9d  mov     ecx, 3
0x180015da2  int     29h; Win8: RtlFailFast(ecx)
0x180015da4  call    ReleaseWriteLock
0x180015da9  xor     r14d, r14d
0x180015dac  lea     ebx, [r14+1]
0x180015db0  jmp     short loc_180015DF8
0x180015db2  xor     r14d, r14d
0x180015db5  lea     ebx, [r14+1]
0x180015db9  cmp     cs:qword_18002B8A8, r14
0x180015dc0  jz      short loc_180015DF8
0x180015dc2  lea     rdx, aFailedToGetOpa_0; "Failed to get opaque ptr : %x"
0x180015dc9  mov     word ptr [rsp+880h+var_850], r14w
0x180015dcf  lea     rcx, [rsp+880h+var_850]
0x180015dd4  call    FormatRRASErrorString
0x180015dd9  mov     rdx, cs:qword_18002B8A8
0x180015de0  lea     r8, [rsp+880h+var_850]
0x180015de5  mov     rcx, cs:gMgmEtwContext
0x180015dec  mov     rax, cs:gMgmTemplateFunc
0x180015df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015df8  mov     rcx, [rsi]
0x180015dfb  xor     rcx, 7754DF32h
0x180015e02  jz      short loc_180015E18
0x180015e04  cmp     [rcx+6Ch], bx
0x180015e08  jz      short loc_180015E18
0x180015e0a  add     rcx, 20h ; ' '
0x180015e0e  call    ReleaseWriteLock
0x180015e13  mov     ebx, r14d
0x180015e16  jmp     short loc_180015E5F
0x180015e18  cmp     cs:qword_18002B8A8, r14
0x180015e1f  mov     ebx, 6
0x180015e24  jz      short loc_180015E5F
0x180015e26  mov     r8d, ebx
0x180015e29  mov     word ptr [rsp+880h+var_850], r14w
0x180015e2f  lea     rdx, aFailedToLockDe_0; "Failed to lock dest : %x"
0x180015e36  lea     rcx, [rsp+880h+var_850]
0x180015e3b  call    FormatRRASErrorString
0x180015e40  mov     rdx, cs:qword_18002B8A8
0x180015e47  lea     r8, [rsp+880h+var_850]
0x180015e4c  mov     rcx, cs:gMgmEtwContext
0x180015e53  mov     rax, cs:gMgmTemplateFunc
0x180015e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e5f  test    r13d, r13d
0x180015e62  jz      loc_180015EEA
0x180015e68  mov     r8, [rsi]; DestHandle
0x180015e6b  xor     r9d, r9d; MarkDest
0x180015e6e  mov     rdx, cs:g_hNotificationHandle; NotifyHandle
0x180015e75  mov     rcx, cs:g_hRtmHandle; RtmRegHandle
0x180015e7c  call    RtmMarkDestForChangeNotification
0x180015e81  mov     ebx, eax
0x180015e83  test    eax, eax
0x180015e85  jz      short loc_180015EEA
0x180015e87  cmp     cs:qword_18002B8A8, r14
0x180015e8e  jz      short loc_180015EEA
0x180015e90  mov     r8d, eax
0x180015e93  lea     rdx, aFailedToUnmark; "Failed to unmark DEST: %x"
0x180015e9a  jmp     short loc_180015EBB
0x180015e9c  call    ReleaseWriteLock
0x180015ea1  jmp     short loc_180015EEA
0x180015ea3  cmp     cs:qword_18002B8A8, r14
0x180015eaa  mov     ebx, 6
0x180015eaf  jz      short loc_180015EEA
0x180015eb1  mov     r8d, ebx
0x180015eb4  lea     rdx, aFailedToLockDe_0; "Failed to lock dest : %x"
0x180015ebb  lea     rcx, [rsp+880h+var_850]
0x180015ec0  mov     word ptr [rsp+880h+var_850], r14w
0x180015ec6  call    FormatRRASErrorString
0x180015ecb  mov     rdx, cs:qword_18002B8A8
0x180015ed2  lea     r8, [rsp+880h+var_850]
0x180015ed7  mov     rcx, cs:gMgmEtwContext
0x180015ede  mov     rax, cs:gMgmTemplateFunc
0x180015ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015eea  mov     rcx, cs:hHeap; hHeap
0x180015ef1  mov     r8, r12; lpMem
0x180015ef4  xor     edx, edx; dwFlags
0x180015ef6  call    cs:__imp_HeapFree
0x180015efc  jmp     short loc_180015F29
0x180015efe  mov     rdx, cs:qword_18002B8A8
0x180015f05  mov     ebx, 216h
0x180015f0a  test    rdx, rdx
0x180015f0d  jz      short loc_180015F29
0x180015f0f  mov     rcx, cs:gMgmEtwContext
0x180015f16  lea     r8, aArithmaticOver; "Arithmatic Overflow Error. Failed to al"...
0x180015f1d  mov     rax, cs:gMgmTemplateFunc
0x180015f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f29  mov     eax, ebx
0x180015f2b  mov     rcx, [rbp+780h+var_50]
0x180015f32  xor     rcx, rsp; StackCookie
0x180015f35  call    __security_check_cookie
0x180015f3a  add     rsp, 848h
0x180015f41  pop     r15
0x180015f43  pop     r14
0x180015f45  pop     r13
0x180015f47  pop     r12
0x180015f49  pop     rdi
0x180015f4a  pop     rsi
0x180015f4b  pop     rbx
0x180015f4c  pop     rbp
0x180015f4d  retn
```
