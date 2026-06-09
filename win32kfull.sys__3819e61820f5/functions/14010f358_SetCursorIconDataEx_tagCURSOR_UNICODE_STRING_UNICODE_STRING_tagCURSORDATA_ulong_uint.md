# _SetCursorIconDataEx(tagCURSOR *,_UNICODE_STRING *,_UNICODE_STRING *,tagCURSORDATA *,ulong,uint)

- ea: `0x14010f358`
- end: `0x14010fa69`
- name: `?_SetCursorIconDataEx@@YA_NPEAUtagCURSOR@@PEAU_UNICODE_STRING@@1PEAUtagCURSORDATA@@KI@Z`
- size: `1809`
- prototype: `char __fastcall(struct tagCURSOR *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct tagCURSORDATA *, unsigned int Size, unsigned int DpiDependentMetric)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x14010e9b0`
- `0x14010f1d8`

## callees

- `0x140011784`
- `0x140013204`
- `0x14001bc7c`
- `0x14001be68`
- `0x14001c7dc`
- `0x140060f30`
- `0x1400c11d8`
- `0x1400c2a10`
- `0x14010e950`
- `0x14010f358`
- `0x14010fa70`
- `0x14021f9a8`
- `0x140342020`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14010f961`
- `ntoskrnl!PsGetCurrentProcess` at `0x14010f961`
- `win32kbase!GreReferenceObjectIgnoreOwner` at `0x14010f4af`
- `win32kbase!GreReferenceObjectIgnoreOwner` at `0x14010f73c`
- `win32kbase!GreReferenceObjectIgnoreOwner` at `0x14010f4af`
- `win32kbase!GreReferenceObjectIgnoreOwner` at `0x14010f73c`
- `win32kbase!GreDereferenceObject` at `0x14010fa3a`
- `win32kbase!GreDereferenceObject` at `0x14010fa58`
- `win32kbase!GreDereferenceObject` at `0x14010fa3a`
- `win32kbase!GreDereferenceObject` at `0x14010fa58`
- `win32kbase!UserDeleteAtom` at `0x14010f848`
- `win32kbase!UserDeleteAtom` at `0x14010f848`
- `win32kbase!UserAddAtomEx` at `0x14010f685`
- `win32kbase!UserAddAtomEx` at `0x14010f685`
- `win32kbase!GreSetBitmapOwner` at `0x14010f520`
- `win32kbase!GreSetBitmapOwner` at `0x14010f551`
- `win32kbase!GreSetBitmapOwner` at `0x14010f58c`
- `win32kbase!GreSetBitmapOwner` at `0x14010f520`
- `win32kbase!GreSetBitmapOwner` at `0x14010f551`
- `win32kbase!GreSetBitmapOwner` at `0x14010f58c`
- `win32kbase!GreIncQuotaCount` at `0x14010f52f`
- `win32kbase!GreIncQuotaCount` at `0x14010f560`
- `win32kbase!GreIncQuotaCount` at `0x14010f59b`
- `win32kbase!GreIncQuotaCount` at `0x14010f52f`
- `win32kbase!GreIncQuotaCount` at `0x14010f560`
- `win32kbase!GreIncQuotaCount` at `0x14010f59b`
- `win32kbase!GreDeleteObject` at `0x14010f60f`
- `win32kbase!GreDeleteObject` at `0x14010f6ee`
- `win32kbase!GreDeleteObject` at `0x14010f703`
- `win32kbase!GreDeleteObject` at `0x14010f754`
- `win32kbase!GreDeleteObject` at `0x14010f7c2`
- `win32kbase!GreDeleteObject` at `0x14010f7db`
- `win32kbase!GreDeleteObject` at `0x14010fa07`
- `win32kbase!GreDeleteObject` at `0x14010f60f`
- `win32kbase!GreDeleteObject` at `0x14010f6ee`
- `win32kbase!GreDeleteObject` at `0x14010f703`
- `win32kbase!GreDeleteObject` at `0x14010f754`
- `win32kbase!GreDeleteObject` at `0x14010f7c2`
- `win32kbase!GreDeleteObject` at `0x14010f7db`
- `win32kbase!GreDeleteObject` at `0x14010fa07`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x14010f801`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x14010f801`
- `win32kbase!HMAssignmentLock` at `0x14010f99e`
- `win32kbase!HMAssignmentLock` at `0x14010f99e`
- `win32kbase!Win32FreePool` at `0x14010f71d`
- `win32kbase!Win32FreePool` at `0x14010f823`
- `win32kbase!Win32FreePool` at `0x14010f9c6`
- `win32kbase!Win32FreePool` at `0x14010f71d`
- `win32kbase!Win32FreePool` at `0x14010f823`
- `win32kbase!Win32FreePool` at `0x14010f9c6`
- `win32kbase!HMAssignmentUnlock` at `0x14010f9f3`
- `win32kbase!HMAssignmentUnlock` at `0x14010f9f3`
- `WIN32K!W32GetUserGdiSessionState` at `0x14010f951`
- `WIN32K!W32GetUserGdiSessionState` at `0x14010f951`
- `WIN32K!W32GetUserSessionState` at `0x14010f63a`
- `WIN32K!W32GetUserSessionState` at `0x14010f63a`

## pseudocode

```c
char __fastcall _SetCursorIconDataEx(
        struct tagCURSOR *a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        struct tagCURSORDATA *a4,
        unsigned int Size,
        unsigned int DpiDependentMetric)
{
  struct _UNICODE_STRING *v7; // rax
  int *v9; // r12
  int v10; // r15d
  char v11; // r15
  struct _UNICODE_STRING *v12; // r14
  void *v13; // r9
  int v14; // ecx
  _QWORD *v15; // r12
  void **v16; // r15
  __int64 v17; // rdx
  __int64 v18; // r14
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  HBITMAP v22; // rcx
  __int64 v23; // rcx
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 UserSessionState; // rax
  const wchar_t *Buffer; // r9
  size_t *v32; // r8
  __int64 v33; // rdx
  __int64 v34; // rcx
  unsigned int DpiForSystem; // eax
  char *v36; // rcx
  char *v37; // r9
  char *v38; // r10
  int v39; // ecx
  int v40; // r8d
  int v41; // edx
  __int64 i; // rdx
  unsigned int j; // r14d
  __int64 v44; // rax
  __int64 v45; // r13
  __int64 v46; // rbx
  __int64 v47; // rcx
  __int64 v48; // rcx
  size_t v49; // [rsp+20h] [rbp-D8h]
  __int64 v50; // [rsp+40h] [rbp-B8h] BYREF
  __int64 v51; // [rsp+48h] [rbp-B0h]
  __int64 v52; // [rsp+50h] [rbp-A8h]
  char *v53; // [rsp+58h] [rbp-A0h]
  char *v54; // [rsp+60h] [rbp-98h]
  __int128 v55; // [rsp+68h] [rbp-90h]
  __int128 v56; // [rsp+78h] [rbp-80h]
  __int128 v57; // [rsp+88h] [rbp-70h]
  __int128 v58; // [rsp+98h] [rbp-60h]

  v7 = a3;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  if ( !DpiDependentMetric )
  {
    DpiForSystem = GetDpiForSystem();
    DpiDependentMetric = GetDpiDependentMetric(7, DpiForSystem);
    v7 = a3;
  }
  v9 = (int *)((char *)a1 + 80);
  v53 = (char *)a1 + 80;
  *((_DWORD *)a1 + 20) &= ~0x800u;
  v10 = *((_DWORD *)a4 + 6);
  if ( (v10 & 8) != 0 && *((_QWORD *)a1 + 12) )
    return 0;
  v11 = *((_DWORD *)a1 + 20) | v10;
  v12 = (struct _UNICODE_STRING *)((char *)a1 + 56);
  v54 = (char *)a1 + 56;
  if ( !v7->Length )
  {
    *v12 = *v7;
LABEL_6:
    if ( a2->Buffer )
    {
      AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)&v50);
      UserSessionState = W32GetUserSessionState(v27, v26, v28, v29);
      Buffer = a2->Buffer;
      v52 = UserSessionState + 41556;
      if ( RtlStringCopyWorkerW((NTSTRSAFE_PWSTR)(UserSessionState + 41556), 0x100u, v32, Buffer, v49) < 0 )
        *((_WORD *)a1 + 36) = 0;
      else
        *((_WORD *)a1 + 36) = UserAddAtomEx(v52, 0, 2);
      if ( (_BYTE)v50 )
        --*(_DWORD *)(v51 + 28);
      if ( !*((_WORD *)a1 + 36) )
      {
        if ( (v11 & 8) == 0 )
        {
          if ( *((_QWORD *)a4 + 4) )
            ((void (*)(void))GreDeleteObject)();
          if ( *((_QWORD *)a4 + 5) )
            ((void (*)(void))GreDeleteObject)();
        }
        if ( !v12->Length )
          return 0;
        Win32FreePool(*((void **)a1 + 8));
        goto LABEL_42;
      }
    }
    v13 = 0;
    if ( (v11 & 8) != 0 )
    {
      if ( Size )
        v13 = (void *)Win32AllocPoolWithQuotaZInit(Size, 1969451861);
      if ( !v13 )
      {
        if ( v12->Length )
        {
          Win32FreePool(*((void **)a1 + 8));
          *((_QWORD *)a1 + 8) = 0;
          v12->Length = 0;
          *((_WORD *)a1 + 29) = 0;
        }
        if ( *((_WORD *)a1 + 36) )
        {
          UserDeleteAtom();
          *((_WORD *)a1 + 36) = 0;
        }
        return 0;
      }
    }
    *v9 |= *((_DWORD *)a4 + 6);
    v14 = *v9;
    *((_WORD *)a1 + 37) = *((_WORD *)a4 + 8);
    *((_DWORD *)a1 + 19) = DpiDependentMetric;
    v15 = (_QWORD *)((char *)a1 + 88);
    v16 = (void **)((char *)a1 + 96);
    if ( (v14 & 8) != 0 )
    {
      *(_OWORD *)v15 = *((_OWORD *)a4 + 6);
      *(_OWORD *)((char *)a1 + 104) = *((_OWORD *)a4 + 7);
      *((_QWORD *)a1 + 15) = *((_QWORD *)a4 + 16);
      *v16 = v13;
      RtlCopyVolatileMemory(v13, *((const void **)a4 + 13), Size);
      v36 = (char *)*v16;
      v37 = (char *)*v16 + *((_QWORD *)a4 + 14);
      *((_QWORD *)a1 + 13) = v37;
      v38 = &v36[*((_QWORD *)a4 + 15)];
      *((_QWORD *)a1 + 14) = v38;
      v39 = 0;
      v40 = *((_DWORD *)a1 + 23);
      while ( v39 < v40 )
      {
        v41 = *(_DWORD *)&v37[4 * v39];
        if ( v41 < 0 || v41 >= *(_DWORD *)v15 )
          goto LABEL_76;
        ++v39;
      }
      for ( i = 0; (int)i < v40; i = (unsigned int)(i + 1) )
      {
        if ( (unsigned int)(100 * *(_DWORD *)&v38[4 * (unsigned int)i]) >= 6 )
          break;
      }
      if ( (_DWORD)i == v40 )
      {
LABEL_76:
        v47 = 87;
LABEL_77:
        UserSetLastError(v47);
        Win32FreePool(*v16);
        *v16 = 0;
        *((_QWORD *)a1 + 13) = 0;
        *((_QWORD *)a1 + 14) = 0;
        *(_DWORD *)v15 = 0;
        *((_DWORD *)a1 + 23) = 0;
        *((_DWORD *)a1 + 30) = 0;
        return 0;
      }
      for ( j = 0; (signed int)j < *(_DWORD *)v15; ++j )
      {
        LOBYTE(i) = 3;
        v44 = HMValidateHandleWithDescriptor(*((_QWORD *)*v16 + (int)j), i);
        v45 = v44;
        if ( !v44
          || (*(_DWORD *)(v44 + 80) & 0x48) != 0x40
          || (v46 = *(_QWORD *)(W32GetUserGdiSessionState() + 40), PsGetCurrentProcess() != v46)
          && !*(_QWORD *)(v45 + 24) )
        {
          while ( (--j & 0x80000000) == 0 )
            HMAssignmentUnlock((char *)*v16 + 8 * j);
          v47 = 1402;
          goto LABEL_77;
        }
        *((_QWORD *)*v16 + (int)j) = 0;
        v50 = (__int64)*v16 + 8 * (int)j;
        v51 = v45;
        HMAssignmentLock(&v50, 0);
      }
    }
    else
    {
      v18 = *((_QWORD *)_GetCurrentLogicalCursorThread() + 57);
      *((_QWORD *)a4 + 6) = 0;
      *(_OWORD *)((char *)a4 + 56) = 0;
      *(_OWORD *)((char *)a1 + 84) = *(_OWORD *)((char *)a4 + 28);
      *(_OWORD *)((char *)a1 + 100) = *(_OWORD *)((char *)a4 + 44);
      *(_OWORD *)((char *)a1 + 116) = *(_OWORD *)((char *)a4 + 60);
      *(_OWORD *)((char *)a1 + 132) = *(_OWORD *)((char *)a4 + 76);
      *((_DWORD *)a1 + 37) = *((_DWORD *)a4 + 23);
      *v15 = 0;
      *v16 = 0;
      v19 = *((_QWORD *)a4 + 4);
      if ( v19 )
      {
        LOBYTE(v17) = 5;
        if ( (int)GreReferenceObjectIgnoreOwner(v19, v17) < 0 )
        {
          GreDeleteObject(*((_QWORD *)a4 + 4));
          v25 = *((_QWORD *)a4 + 5);
          if ( v25 )
            GreDeleteObject(v25);
          return 0;
        }
      }
      v20 = *((_QWORD *)a4 + 5);
      if ( v20 )
      {
        LOBYTE(v17) = 5;
        if ( (int)GreReferenceObjectIgnoreOwner(v20, v17) < 0 )
        {
          GreDeleteObject(*((_QWORD *)a4 + 5));
          v34 = *((_QWORD *)a4 + 4);
LABEL_85:
          if ( v34 )
          {
            LOBYTE(v33) = 5;
            GreDereferenceObject(v34, v33, 0);
          }
          return 0;
        }
      }
      if ( !*((_DWORD *)a1 + 35)
        || !*((_DWORD *)a1 + 36)
        || (v21 = *((_QWORD *)a4 + 4)) == 0
        || *((_QWORD *)a4 + 5)
        && (!(unsigned int)GreExtGetObjectW(v21)
         || !(unsigned int)GreExtGetObjectW(*((_QWORD *)a4 + 5))
         || DWORD2(v57) != SDWORD2(v55) >> 1 && DWORD2(v57) != DWORD2(v55)
         || SDWORD1(v57) < SDWORD1(v55)) )
      {
        UserSetLastError(87);
        v48 = *((_QWORD *)a4 + 4);
        if ( v48 )
        {
          LOBYTE(v33) = 5;
          GreDereferenceObject(v48, v33, 0);
        }
        v34 = *((_QWORD *)a4 + 5);
        goto LABEL_85;
      }
      *v15 = *((_QWORD *)a4 + 4);
      v22 = (HBITMAP)*((_QWORD *)a4 + 5);
      *v16 = v22;
      *((_QWORD *)a1 + 16) = ProcessAlphaBitmap(v22);
      GreSetBitmapOwner(*v15, 0);
      GreIncQuotaCount(v18);
      if ( *v16 )
      {
        GreSetBitmapOwner(*v16, 0);
        GreIncQuotaCount(v18);
      }
      v23 = *((_QWORD *)a1 + 16);
      if ( v23 )
      {
        GreSetBitmapOwner(v23, 0);
        GreIncQuotaCount(v18);
      }
    }
    LinkCursor(a1);
    return 1;
  }
  if ( (unsigned int)AllocateUnicodeString((char *)a1 + 56, v7) )
    goto LABEL_6;
  if ( (v11 & 8) == 0 )
  {
    if ( *((_QWORD *)a4 + 4) )
      ((void (*)(void))GreDeleteObject)();
    if ( *((_QWORD *)a4 + 5) )
      ((void (*)(void))GreDeleteObject)();
  }
LABEL_42:
  *((_QWORD *)a1 + 8) = 0;
  v12->Length = 0;
  *((_WORD *)a1 + 29) = 0;
  return 0;
}

```

## disassembly

```asm
0x14010f358  mov     r11, rsp
0x14010f35b  mov     [r11+20h], r9
0x14010f35f  mov     [r11+18h], r8
0x14010f363  mov     [r11+10h], rdx
0x14010f367  mov     [r11+8], rcx
0x14010f36b  push    rbx
0x14010f36c  push    rsi
0x14010f36d  push    rdi
0x14010f36e  push    r12
0x14010f370  push    r13
0x14010f372  push    r14
0x14010f374  push    r15
0x14010f376  sub     rsp, 0C0h
0x14010f37d  mov     rbx, r9
0x14010f380  mov     rax, r8
0x14010f383  mov     rsi, rcx
0x14010f386  xorps   xmm0, xmm0
0x14010f389  movups  [rsp+0F8h+var_90], xmm0
0x14010f38e  movups  [rsp+0F8h+var_80], xmm0
0x14010f393  xorps   xmm1, xmm1
0x14010f396  movups  xmmword ptr [r11-70h], xmm1
0x14010f39b  movups  xmmword ptr [r11-60h], xmm1
0x14010f3a0  xor     edi, edi
0x14010f3a2  cmp     [rsp+0F8h+arg_28], edi
0x14010f3a9  jz      loc_14010F769
0x14010f3af  lea     r12, [rsi+50h]
0x14010f3b3  mov     [rsp+0F8h+var_A0], r12
0x14010f3b8  btr     dword ptr [r12], 0Bh
0x14010f3be  mov     edx, [r12]
0x14010f3c2  lea     rcx, [rbx+18h]
0x14010f3c6  mov     [rsp+0F8h+var_C0], rcx
0x14010f3cb  mov     r15d, [rcx]
0x14010f3ce  mov     r13b, 8
0x14010f3d1  test    r13b, r15b
0x14010f3d4  jnz     loc_14010F78E
0x14010f3da  or      r15d, edx
0x14010f3dd  mov     [rsp+0F8h+var_C4], r15d
0x14010f3e2  lea     r14, [rsi+38h]
0x14010f3e6  mov     [rsp+0F8h+var_98], r14
0x14010f3eb  cmp     [rax], di
0x14010f3ee  jnz     loc_14010F79D
0x14010f3f4  movups  xmm0, xmmword ptr [rax]
0x14010f3f7  movdqu  xmmword ptr [r14], xmm0
0x14010f3fc  mov     rax, [rsp+0F8h+arg_8]
0x14010f404  cmp     [rax+8], rdi
0x14010f408  jnz     loc_14010F62F
0x14010f40e  mov     r9, rdi
0x14010f411  test    r13b, r15b
0x14010f414  jnz     loc_14010F7EC
0x14010f41a  mov     rax, [rsp+0F8h+var_C0]
0x14010f41f  mov     eax, [rax]
0x14010f421  or      [r12], eax
0x14010f425  mov     ecx, [r12]
0x14010f429  movzx   eax, word ptr [rbx+10h]
0x14010f42d  mov     [rsi+4Ah], ax
0x14010f431  mov     eax, [rsp+0F8h+arg_28]
0x14010f438  mov     [rsi+4Ch], eax
0x14010f43b  lea     r12, [rsi+58h]
0x14010f43f  mov     [rsp+0F8h+arg_18], r12
0x14010f447  lea     r15, [rsi+60h]
0x14010f44b  mov     [rsp+0F8h+var_C0], r15
0x14010f450  test    r13b, cl
0x14010f453  jnz     loc_14010F85D
0x14010f459  call    ?_GetCurrentLogicalCursorThread@@YAPEAUtagTHREADINFO@@XZ; _GetCurrentLogicalCursorThread(void)
0x14010f45e  mov     r14, [rax+1C8h]
0x14010f465  mov     [rbx+30h], rdi
0x14010f469  xorps   xmm0, xmm0
0x14010f46c  movdqu  xmmword ptr [rbx+38h], xmm0
0x14010f471  movups  xmm0, xmmword ptr [rbx+1Ch]
0x14010f475  movups  xmmword ptr [rsi+54h], xmm0
0x14010f479  movups  xmm1, xmmword ptr [rbx+2Ch]
0x14010f47d  movups  xmmword ptr [rsi+64h], xmm1
0x14010f481  movups  xmm0, xmmword ptr [rbx+3Ch]
0x14010f485  movups  xmmword ptr [rsi+74h], xmm0
0x14010f489  movups  xmm1, xmmword ptr [rbx+4Ch]
0x14010f48d  movups  xmmword ptr [rsi+84h], xmm1
0x14010f494  mov     eax, [rbx+5Ch]
0x14010f497  mov     [rsi+94h], eax
0x14010f49d  mov     [r12], rdi
0x14010f4a1  mov     [r15], rdi
0x14010f4a4  mov     rcx, [rbx+20h]
0x14010f4a8  test    rcx, rcx
0x14010f4ab  jz      short loc_14010F4C3
0x14010f4ad  mov     dl, 5
0x14010f4af  call    cs:__imp_GreReferenceObjectIgnoreOwner
0x14010f4b6  nop     dword ptr [rax+rax+00h]
0x14010f4bb  test    eax, eax
0x14010f4bd  js      loc_14010F60B
0x14010f4c3  mov     rcx, [rbx+28h]
0x14010f4c7  test    rcx, rcx
0x14010f4ca  jnz     loc_14010F73A
0x14010f4d0  cmp     [rsi+8Ch], edi
0x14010f4d6  jz      loc_14010FA22
0x14010f4dc  cmp     [rsi+90h], edi
0x14010f4e2  jz      loc_14010FA22
0x14010f4e8  mov     rcx, [rbx+20h]; int
0x14010f4ec  test    rcx, rcx
0x14010f4ef  jz      loc_14010FA22
0x14010f4f5  cmp     [rbx+28h], rdi
0x14010f4f9  jnz     loc_14010F5A9
0x14010f4ff  mov     rax, [rbx+20h]
0x14010f503  mov     [r12], rax
0x14010f507  mov     rcx, [rbx+28h]; HBITMAP
0x14010f50b  mov     [r15], rcx
0x14010f50e  call    ?ProcessAlphaBitmap@@YAPEAUHBITMAP__@@PEAU1@@Z; ProcessAlphaBitmap(HBITMAP__ *)
0x14010f513  mov     [rsi+80h], rax
0x14010f51a  xor     edx, edx
0x14010f51c  mov     rcx, [r12]
0x14010f520  call    cs:__imp_GreSetBitmapOwner
0x14010f527  nop     dword ptr [rax+rax+00h]
0x14010f52c  mov     rcx, r14
0x14010f52f  call    cs:__imp_GreIncQuotaCount
0x14010f536  nop     dword ptr [rax+rax+00h]
0x14010f53b  mov     rcx, [r15]
0x14010f53e  test    rcx, rcx
0x14010f541  jnz     short loc_14010F58A
0x14010f543  mov     rcx, [rsi+80h]
0x14010f54a  test    rcx, rcx
0x14010f54d  jz      short loc_14010F56C
0x14010f54f  xor     edx, edx
0x14010f551  call    cs:__imp_GreSetBitmapOwner
0x14010f558  nop     dword ptr [rax+rax+00h]
0x14010f55d  mov     rcx, r14
0x14010f560  call    cs:__imp_GreIncQuotaCount
0x14010f567  nop     dword ptr [rax+rax+00h]
0x14010f56c  mov     rcx, rsi; struct tagCURSOR *
0x14010f56f  call    ?LinkCursor@@YAXPEAUtagCURSOR@@@Z; LinkCursor(tagCURSOR *)
0x14010f574  mov     al, 1
0x14010f576  add     rsp, 0C0h
0x14010f57d  pop     r15
0x14010f57f  pop     r14
0x14010f581  pop     r13
0x14010f583  pop     r12
0x14010f585  pop     rdi
0x14010f586  pop     rsi
0x14010f587  pop     rbx
0x14010f588  retn
0x14010f58a  xor     edx, edx
0x14010f58c  call    cs:__imp_GreSetBitmapOwner
0x14010f593  nop     dword ptr [rax+rax+00h]
0x14010f598  mov     rcx, r14
0x14010f59b  call    cs:__imp_GreIncQuotaCount
0x14010f5a2  nop     dword ptr [rax+rax+00h]
0x14010f5a7  jmp     short loc_14010F543
0x14010f5a9  lea     r8, [rsp+0F8h+var_90]
0x14010f5ae  mov     r13d, 20h ; ' '
0x14010f5b4  mov     edx, r13d
0x14010f5b7  call    GreExtGetObjectW
0x14010f5bc  test    eax, eax
0x14010f5be  jz      loc_14010FA22
0x14010f5c4  lea     r8, [rsp+0F8h+var_70]
0x14010f5cc  mov     edx, r13d
0x14010f5cf  mov     rcx, [rbx+28h]; int
0x14010f5d3  call    GreExtGetObjectW
0x14010f5d8  test    eax, eax
0x14010f5da  jz      loc_14010FA22
0x14010f5e0  mov     eax, dword ptr [rsp+0F8h+var_90+8]
0x14010f5e4  sar     eax, 1
0x14010f5e6  mov     ecx, [rsp+0F8h+var_68]
0x14010f5ed  cmp     ecx, eax
0x14010f5ef  jnz     loc_14010FA18
0x14010f5f5  mov     eax, [rsp+0F8h+var_6C]
0x14010f5fc  cmp     eax, dword ptr [rsp+0F8h+var_90+4]
0x14010f600  jge     loc_14010F4FF
0x14010f606  jmp     loc_14010FA22
0x14010f60b  mov     rcx, [rbx+20h]
0x14010f60f  call    cs:__imp_GreDeleteObject
0x14010f616  nop     dword ptr [rax+rax+00h]
0x14010f61b  mov     rcx, [rbx+28h]
0x14010f61f  test    rcx, rcx
0x14010f622  jnz     loc_14010FA07
0x14010f628  xor     al, al
0x14010f62a  jmp     loc_14010F576
0x14010f62f  lea     rcx, [rsp+0F8h+var_B8]; this
0x14010f634  call    ??0AtomicExecutionCheck@@QEAA@XZ; AtomicExecutionCheck::AtomicExecutionCheck(void)
0x14010f639  nop
0x14010f63a  call    cs:__imp_W32GetUserSessionState
0x14010f641  nop     dword ptr [rax+rax+00h]
0x14010f646  mov     rcx, [rsp+0F8h+arg_8]
0x14010f64e  mov     r9, [rcx+8]; pszSrc
0x14010f652  add     rax, 0A254h
0x14010f658  mov     [rsp+0F8h+var_A8], rax
0x14010f65d  mov     [rsp+0F8h+var_C8], edi
0x14010f661  mov     [rsp+0F8h+var_C8], edi
0x14010f665  mov     edx, 100h; cchDest
0x14010f66a  mov     rcx, rax; pszDest
0x14010f66d  call    RtlStringCopyWorkerW
0x14010f672  mov     [rsp+0F8h+var_C8], eax
0x14010f676  test    eax, eax
0x14010f678  js      short loc_14010F697
0x14010f67a  xor     edx, edx
0x14010f67c  lea     r8d, [rdx+2]
0x14010f680  mov     rcx, [rsp+0F8h+var_A8]
0x14010f685  call    cs:__imp_UserAddAtomEx
0x14010f68c  nop     dword ptr [rax+rax+00h]
0x14010f691  mov     [rsi+48h], ax
0x14010f695  jmp     short loc_14010F69B
0x14010f697  mov     [rsi+48h], di
0x14010f69b  jmp     short loc_14010F6C7
0x14010f69d  xor     eax, eax
0x14010f69f  mov     rsi, [rsp+0F8h+arg_0]
0x14010f6a7  mov     [rsi+48h], ax
0x14010f6ab  xor     edi, edi
0x14010f6ad  mov     r13b, 8
0x14010f6b0  mov     rbx, [rsp+0F8h+arg_18]
0x14010f6b8  mov     r12, [rsp+0F8h+var_A0]
0x14010f6bd  mov     r14, [rsp+0F8h+var_98]
0x14010f6c2  mov     r15d, [rsp+0F8h+var_C4]
0x14010f6c7  cmp     byte ptr [rsp+0F8h+var_B8], dil
0x14010f6cc  jz      short loc_14010F6D6
0x14010f6ce  mov     rax, [rsp+0F8h+var_B0]
0x14010f6d3  dec     dword ptr [rax+1Ch]
0x14010f6d6  cmp     [rsi+48h], di
0x14010f6da  jnz     loc_14010F40E
0x14010f6e0  test    r13b, r15b
0x14010f6e3  jnz     short loc_14010F70F
0x14010f6e5  mov     rcx, [rbx+20h]
0x14010f6e9  test    rcx, rcx
0x14010f6ec  jz      short loc_14010F6FA
0x14010f6ee  call    cs:__imp_GreDeleteObject
0x14010f6f5  nop     dword ptr [rax+rax+00h]
0x14010f6fa  mov     rcx, [rbx+28h]
0x14010f6fe  test    rcx, rcx
0x14010f701  jz      short loc_14010F70F
0x14010f703  call    cs:__imp_GreDeleteObject
0x14010f70a  nop     dword ptr [rax+rax+00h]
0x14010f70f  cmp     [r14], di
0x14010f713  jz      loc_14010F628
0x14010f719  mov     rcx, [rsi+40h]
0x14010f71d  call    cs:__imp_Win32FreePool
0x14010f724  nop     dword ptr [rax+rax+00h]
0x14010f729  mov     [rsi+40h], rdi
0x14010f72d  mov     [r14], di
0x14010f731  mov     [rsi+3Ah], di
0x14010f735  jmp     loc_14010F628
0x14010f73a  mov     dl, 5
0x14010f73c  call    cs:__imp_GreReferenceObjectIgnoreOwner
0x14010f743  nop     dword ptr [rax+rax+00h]
0x14010f748  test    eax, eax
0x14010f74a  jns     loc_14010F4D0
0x14010f750  mov     rcx, [rbx+28h]
0x14010f754  call    cs:__imp_GreDeleteObject
0x14010f75b  nop     dword ptr [rax+rax+00h]
0x14010f760  mov     rcx, [rbx+20h]
0x14010f764  jmp     loc_14010FA4A
0x14010f769  call    GetDpiForSystem
0x14010f76e  mov     edx, eax
0x14010f770  mov     ecx, 7
0x14010f775  call    GetDpiDependentMetric
0x14010f77a  mov     [rsp+0F8h+arg_28], eax
0x14010f781  mov     rax, [rsp+0F8h+arg_10]
0x14010f789  jmp     loc_14010F3AF
0x14010f78e  cmp     [rsi+60h], rdi
0x14010f792  jnz     loc_14010F628
0x14010f798  jmp     loc_14010F3DA
0x14010f79d  mov     rdx, rax
0x14010f7a0  mov     rcx, r14
0x14010f7a3  call    AllocateUnicodeString
0x14010f7a8  test    eax, eax
0x14010f7aa  jnz     loc_14010F3FC
0x14010f7b0  test    r13b, r15b
0x14010f7b3  jnz     loc_14010F729
0x14010f7b9  mov     rcx, [rbx+20h]
0x14010f7bd  test    rcx, rcx
0x14010f7c0  jz      short loc_14010F7CE
0x14010f7c2  call    cs:__imp_GreDeleteObject
0x14010f7c9  nop     dword ptr [rax+rax+00h]
0x14010f7ce  mov     rcx, [rbx+28h]
0x14010f7d2  test    rcx, rcx
0x14010f7d5  jz      loc_14010F729
0x14010f7db  call    cs:__imp_GreDeleteObject
0x14010f7e2  nop     dword ptr [rax+rax+00h]
0x14010f7e7  jmp     loc_14010F729
0x14010f7ec  cmp     dword ptr [rsp+0F8h+Size], edi
0x14010f7f3  jz      short loc_14010F810
0x14010f7f5  mov     ecx, dword ptr [rsp+0F8h+Size]
0x14010f7fc  mov     edx, 75637355h
0x14010f801  call    cs:__imp_Win32AllocPoolWithQuotaZInit
0x14010f808  nop     dword ptr [rax+rax+00h]
0x14010f80d  mov     r9, rax
0x14010f810  test    r9, r9
0x14010f813  jnz     loc_14010F41A
0x14010f819  cmp     [r14], di
0x14010f81d  jz      short loc_14010F83B
0x14010f81f  mov     rcx, [rsi+40h]
0x14010f823  call    cs:__imp_Win32FreePool
0x14010f82a  nop     dword ptr [rax+rax+00h]
0x14010f82f  mov     [rsi+40h], rdi
0x14010f833  mov     [r14], di
0x14010f837  mov     [rsi+3Ah], di
0x14010f83b  movzx   ecx, word ptr [rsi+48h]
0x14010f83f  test    cx, cx
0x14010f842  jz      loc_14010F628
0x14010f848  call    cs:__imp_UserDeleteAtom
0x14010f84f  nop     dword ptr [rax+rax+00h]
0x14010f854  mov     [rsi+48h], di
0x14010f858  jmp     loc_14010F628
0x14010f85d  movups  xmm0, xmmword ptr [rbx+60h]
0x14010f861  movups  xmmword ptr [r12], xmm0
0x14010f866  movups  xmm1, xmmword ptr [rbx+70h]
  ... truncated ...
```
