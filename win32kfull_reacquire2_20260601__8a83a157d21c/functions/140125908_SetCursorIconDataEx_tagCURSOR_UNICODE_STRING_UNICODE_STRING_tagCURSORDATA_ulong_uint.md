# _SetCursorIconDataEx(tagCURSOR *,_UNICODE_STRING *,_UNICODE_STRING *,tagCURSORDATA *,ulong,uint)

- ea: `0x140125908`
- end: `0x140126019`
- name: `?_SetCursorIconDataEx@@YA_NPEAUtagCURSOR@@PEAU_UNICODE_STRING@@1PEAUtagCURSORDATA@@KI@Z`
- size: `1809`
- prototype: `bool __usercall@<al>(struct tagCURSOR *@<rcx>, struct _UNICODE_STRING *@<rdx>, struct _UNICODE_STRING *@<r8>, struct tagCURSORDATA *@<r9>, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140124f60`
- `0x140125788`

## callees

- `0x140093dfc`
- `0x140093fe8`
- `0x140099860`
- `0x14009a55c`
- `0x1400c2a94`
- `0x1400c4514`
- `0x1400e73e8`
- `0x1400e8c20`
- `0x140124f00`
- `0x140125908`
- `0x140126020`
- `0x140220c00`
- `0x140342fd0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140125f11`
- `ntoskrnl!PsGetCurrentProcess` at `0x140125f11`
- `win32kbase!GreReferenceObjectIgnoreOwner` at `0x140125a5f`
- `win32kbase!GreReferenceObjectIgnoreOwner` at `0x140125cec`
- `win32kbase!GreReferenceObjectIgnoreOwner` at `0x140125a5f`
- `win32kbase!GreReferenceObjectIgnoreOwner` at `0x140125cec`
- `win32kbase!GreDereferenceObject` at `0x140125fea`
- `win32kbase!GreDereferenceObject` at `0x140126008`
- `win32kbase!GreDereferenceObject` at `0x140125fea`
- `win32kbase!GreDereferenceObject` at `0x140126008`
- `win32kbase!UserDeleteAtom` at `0x140125df8`
- `win32kbase!UserDeleteAtom` at `0x140125df8`
- `win32kbase!UserAddAtomEx` at `0x140125c35`
- `win32kbase!UserAddAtomEx` at `0x140125c35`
- `win32kbase!GreSetBitmapOwner` at `0x140125ad0`
- `win32kbase!GreSetBitmapOwner` at `0x140125b01`
- `win32kbase!GreSetBitmapOwner` at `0x140125b3c`
- `win32kbase!GreSetBitmapOwner` at `0x140125ad0`
- `win32kbase!GreSetBitmapOwner` at `0x140125b01`
- `win32kbase!GreSetBitmapOwner` at `0x140125b3c`
- `win32kbase!GreIncQuotaCount` at `0x140125adf`
- `win32kbase!GreIncQuotaCount` at `0x140125b10`
- `win32kbase!GreIncQuotaCount` at `0x140125b4b`
- `win32kbase!GreIncQuotaCount` at `0x140125adf`
- `win32kbase!GreIncQuotaCount` at `0x140125b10`
- `win32kbase!GreIncQuotaCount` at `0x140125b4b`
- `win32kbase!GreDeleteObject` at `0x140125bbf`
- `win32kbase!GreDeleteObject` at `0x140125c9e`
- `win32kbase!GreDeleteObject` at `0x140125cb3`
- `win32kbase!GreDeleteObject` at `0x140125d04`
- `win32kbase!GreDeleteObject` at `0x140125d72`
- `win32kbase!GreDeleteObject` at `0x140125d8b`
- `win32kbase!GreDeleteObject` at `0x140125fb7`
- `win32kbase!GreDeleteObject` at `0x140125bbf`
- `win32kbase!GreDeleteObject` at `0x140125c9e`
- `win32kbase!GreDeleteObject` at `0x140125cb3`
- `win32kbase!GreDeleteObject` at `0x140125d04`
- `win32kbase!GreDeleteObject` at `0x140125d72`
- `win32kbase!GreDeleteObject` at `0x140125d8b`
- `win32kbase!GreDeleteObject` at `0x140125fb7`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x140125db1`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x140125db1`
- `win32kbase!HMAssignmentLock` at `0x140125f4e`
- `win32kbase!HMAssignmentLock` at `0x140125f4e`
- `win32kbase!Win32FreePool` at `0x140125ccd`
- `win32kbase!Win32FreePool` at `0x140125dd3`
- `win32kbase!Win32FreePool` at `0x140125f76`
- `win32kbase!Win32FreePool` at `0x140125ccd`
- `win32kbase!Win32FreePool` at `0x140125dd3`
- `win32kbase!Win32FreePool` at `0x140125f76`
- `win32kbase!HMAssignmentUnlock` at `0x140125fa3`
- `win32kbase!HMAssignmentUnlock` at `0x140125fa3`
- `WIN32K!W32GetUserGdiSessionState` at `0x140125f01`
- `WIN32K!W32GetUserGdiSessionState` at `0x140125f01`
- `WIN32K!W32GetUserSessionState` at `0x140125bea`
- `WIN32K!W32GetUserSessionState` at `0x140125bea`

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
  HPALETTE v21; // rcx
  HBITMAP v22; // rcx
  __int64 v23; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 UserSessionState; // rax
  const wchar_t *Buffer; // r9
  size_t *v29; // r8
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rcx
  unsigned int DpiForSystem; // eax
  __int64 v35; // rcx
  __int64 v36; // rcx
  char *v37; // rcx
  char *v38; // r9
  char *v39; // r10
  int v40; // ecx
  int v41; // r8d
  int v42; // edx
  __int64 i; // rdx
  unsigned int j; // r14d
  __int64 v45; // rax
  __int64 v46; // r13
  __int64 v47; // rcx
  __int64 v48; // rbx
  __int64 v49; // rcx
  __int64 v50; // rcx
  size_t v51; // [rsp+20h] [rbp-D8h]
  __int64 v52; // [rsp+40h] [rbp-B8h] BYREF
  __int64 v53; // [rsp+48h] [rbp-B0h]
  __int64 v54; // [rsp+50h] [rbp-A8h]
  char *v55; // [rsp+58h] [rbp-A0h]
  char *v56; // [rsp+60h] [rbp-98h]
  __int128 v57; // [rsp+68h] [rbp-90h]
  __int128 v58; // [rsp+78h] [rbp-80h]
  __int128 v59; // [rsp+88h] [rbp-70h]
  __int128 v60; // [rsp+98h] [rbp-60h]

  v7 = a3;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  if ( !DpiDependentMetric )
  {
    DpiForSystem = GetDpiForSystem(a1);
    DpiDependentMetric = GetDpiDependentMetric(7, DpiForSystem);
    v7 = a3;
  }
  v9 = (int *)((char *)a1 + 80);
  v55 = (char *)a1 + 80;
  *((_DWORD *)a1 + 20) &= ~0x800u;
  v10 = *((_DWORD *)a4 + 6);
  if ( (v10 & 8) != 0 && *((_QWORD *)a1 + 12) )
    return 0;
  v11 = *((_DWORD *)a1 + 20) | v10;
  v12 = (struct _UNICODE_STRING *)((char *)a1 + 56);
  v56 = (char *)a1 + 56;
  if ( !v7->Length )
  {
    *v12 = *v7;
LABEL_6:
    if ( a2->Buffer )
    {
      AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)&v52);
      UserSessionState = W32GetUserSessionState(v26);
      Buffer = a2->Buffer;
      v54 = UserSessionState + 41556;
      if ( RtlStringCopyWorkerW((NTSTRSAFE_PWSTR)(UserSessionState + 41556), 0x100u, v29, Buffer, v51) < 0 )
        *((_WORD *)a1 + 36) = 0;
      else
        *((_WORD *)a1 + 36) = UserAddAtomEx(v54, 0, 2);
      if ( (_BYTE)v52 )
        --*(_DWORD *)(v53 + 28);
      if ( !*((_WORD *)a1 + 36) )
      {
        if ( (v11 & 8) == 0 )
        {
          v30 = *((_QWORD *)a4 + 4);
          if ( v30 )
            GreDeleteObject(v30);
          v31 = *((_QWORD *)a4 + 5);
          if ( v31 )
            GreDeleteObject(v31);
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
        v13 = (void *)Win32AllocPoolWithQuotaZInit(Size, 1969451861, a3, 0);
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
      v37 = (char *)*v16;
      v38 = (char *)*v16 + *((_QWORD *)a4 + 14);
      *((_QWORD *)a1 + 13) = v38;
      v39 = &v37[*((_QWORD *)a4 + 15)];
      *((_QWORD *)a1 + 14) = v39;
      v40 = 0;
      v41 = *((_DWORD *)a1 + 23);
      while ( v40 < v41 )
      {
        v42 = *(_DWORD *)&v38[4 * v40];
        if ( v42 < 0 || v42 >= *(_DWORD *)v15 )
          goto LABEL_76;
        ++v40;
      }
      for ( i = 0; (int)i < v41; i = (unsigned int)(i + 1) )
      {
        if ( (unsigned int)(100 * *(_DWORD *)&v39[4 * (unsigned int)i]) >= 6 )
          break;
      }
      if ( (_DWORD)i == v41 )
      {
LABEL_76:
        v49 = 87;
LABEL_77:
        UserSetLastError(v49);
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
        v45 = HMValidateHandleWithDescriptor(*((_QWORD *)*v16 + (int)j), i);
        v46 = v45;
        if ( !v45
          || (v47 = *(unsigned int *)(v45 + 80), LOBYTE(v47) = v47 & 0x48, (_BYTE)v47 != 64)
          || (v48 = *(_QWORD *)(W32GetUserGdiSessionState(v47) + 40), PsGetCurrentProcess() != v48)
          && !*(_QWORD *)(v46 + 24) )
        {
          while ( (--j & 0x80000000) == 0 )
            HMAssignmentUnlock((char *)*v16 + 8 * j);
          v49 = 1402;
          goto LABEL_77;
        }
        *((_QWORD *)*v16 + (int)j) = 0;
        v52 = (__int64)*v16 + 8 * (int)j;
        v53 = v46;
        HMAssignmentLock(&v52, 0);
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
          v33 = *((_QWORD *)a4 + 4);
LABEL_85:
          if ( v33 )
          {
            LOBYTE(v32) = 5;
            GreDereferenceObject(v33, v32, 0);
          }
          return 0;
        }
      }
      if ( !*((_DWORD *)a1 + 35)
        || !*((_DWORD *)a1 + 36)
        || (v21 = (HPALETTE)*((_QWORD *)a4 + 4)) == 0
        || *((_QWORD *)a4 + 5)
        && (!(unsigned int)GreExtGetObjectW(v21)
         || !(unsigned int)GreExtGetObjectW(*((HPALETTE *)a4 + 5))
         || DWORD2(v59) != SDWORD2(v57) >> 1 && DWORD2(v59) != DWORD2(v57)
         || SDWORD1(v59) < SDWORD1(v57)) )
      {
        UserSetLastError(87);
        v50 = *((_QWORD *)a4 + 4);
        if ( v50 )
        {
          LOBYTE(v32) = 5;
          GreDereferenceObject(v50, v32, 0);
        }
        v33 = *((_QWORD *)a4 + 5);
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
    v35 = *((_QWORD *)a4 + 4);
    if ( v35 )
      GreDeleteObject(v35);
    v36 = *((_QWORD *)a4 + 5);
    if ( v36 )
      GreDeleteObject(v36);
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
0x140125908  mov     r11, rsp
0x14012590b  mov     [r11+20h], r9
0x14012590f  mov     [r11+18h], r8
0x140125913  mov     [r11+10h], rdx
0x140125917  mov     [r11+8], rcx
0x14012591b  push    rbx
0x14012591c  push    rsi
0x14012591d  push    rdi
0x14012591e  push    r12
0x140125920  push    r13
0x140125922  push    r14
0x140125924  push    r15
0x140125926  sub     rsp, 0C0h
0x14012592d  mov     rbx, r9
0x140125930  mov     rax, r8
0x140125933  mov     rsi, rcx
0x140125936  xorps   xmm0, xmm0
0x140125939  movups  [rsp+0F8h+var_90], xmm0
0x14012593e  movups  [rsp+0F8h+var_80], xmm0
0x140125943  xorps   xmm1, xmm1
0x140125946  movups  xmmword ptr [r11-70h], xmm1
0x14012594b  movups  xmmword ptr [r11-60h], xmm1
0x140125950  xor     edi, edi
0x140125952  cmp     [rsp+0F8h+arg_28], edi
0x140125959  jz      loc_140125D19
0x14012595f  lea     r12, [rsi+50h]
0x140125963  mov     [rsp+0F8h+var_A0], r12
0x140125968  btr     dword ptr [r12], 0Bh
0x14012596e  mov     edx, [r12]
0x140125972  lea     rcx, [rbx+18h]
0x140125976  mov     [rsp+0F8h+var_C0], rcx
0x14012597b  mov     r15d, [rcx]
0x14012597e  mov     r13b, 8
0x140125981  test    r13b, r15b
0x140125984  jnz     loc_140125D3E
0x14012598a  or      r15d, edx
0x14012598d  mov     [rsp+0F8h+var_C4], r15d
0x140125992  lea     r14, [rsi+38h]
0x140125996  mov     [rsp+0F8h+var_98], r14
0x14012599b  cmp     [rax], di
0x14012599e  jnz     loc_140125D4D
0x1401259a4  movups  xmm0, xmmword ptr [rax]
0x1401259a7  movdqu  xmmword ptr [r14], xmm0
0x1401259ac  mov     rax, [rsp+0F8h+arg_8]
0x1401259b4  cmp     [rax+8], rdi
0x1401259b8  jnz     loc_140125BDF
0x1401259be  mov     r9, rdi
0x1401259c1  test    r13b, r15b
0x1401259c4  jnz     loc_140125D9C
0x1401259ca  mov     rax, [rsp+0F8h+var_C0]
0x1401259cf  mov     eax, [rax]
0x1401259d1  or      [r12], eax
0x1401259d5  mov     ecx, [r12]
0x1401259d9  movzx   eax, word ptr [rbx+10h]
0x1401259dd  mov     [rsi+4Ah], ax
0x1401259e1  mov     eax, [rsp+0F8h+arg_28]
0x1401259e8  mov     [rsi+4Ch], eax
0x1401259eb  lea     r12, [rsi+58h]
0x1401259ef  mov     [rsp+0F8h+arg_18], r12
0x1401259f7  lea     r15, [rsi+60h]
0x1401259fb  mov     [rsp+0F8h+var_C0], r15
0x140125a00  test    r13b, cl
0x140125a03  jnz     loc_140125E0D
0x140125a09  call    ?_GetCurrentLogicalCursorThread@@YAPEAUtagTHREADINFO@@XZ; _GetCurrentLogicalCursorThread(void)
0x140125a0e  mov     r14, [rax+1C8h]
0x140125a15  mov     [rbx+30h], rdi
0x140125a19  xorps   xmm0, xmm0
0x140125a1c  movdqu  xmmword ptr [rbx+38h], xmm0
0x140125a21  movups  xmm0, xmmword ptr [rbx+1Ch]
0x140125a25  movups  xmmword ptr [rsi+54h], xmm0
0x140125a29  movups  xmm1, xmmword ptr [rbx+2Ch]
0x140125a2d  movups  xmmword ptr [rsi+64h], xmm1
0x140125a31  movups  xmm0, xmmword ptr [rbx+3Ch]
0x140125a35  movups  xmmword ptr [rsi+74h], xmm0
0x140125a39  movups  xmm1, xmmword ptr [rbx+4Ch]
0x140125a3d  movups  xmmword ptr [rsi+84h], xmm1
0x140125a44  mov     eax, [rbx+5Ch]
0x140125a47  mov     [rsi+94h], eax
0x140125a4d  mov     [r12], rdi
0x140125a51  mov     [r15], rdi
0x140125a54  mov     rcx, [rbx+20h]
0x140125a58  test    rcx, rcx
0x140125a5b  jz      short loc_140125A73
0x140125a5d  mov     dl, 5
0x140125a5f  call    cs:__imp_GreReferenceObjectIgnoreOwner
0x140125a66  nop     dword ptr [rax+rax+00h]
0x140125a6b  test    eax, eax
0x140125a6d  js      loc_140125BBB
0x140125a73  mov     rcx, [rbx+28h]
0x140125a77  test    rcx, rcx
0x140125a7a  jnz     loc_140125CEA
0x140125a80  cmp     [rsi+8Ch], edi
0x140125a86  jz      loc_140125FD2
0x140125a8c  cmp     [rsi+90h], edi
0x140125a92  jz      loc_140125FD2
0x140125a98  mov     rcx, [rbx+20h]; HPALETTE
0x140125a9c  test    rcx, rcx
0x140125a9f  jz      loc_140125FD2
0x140125aa5  cmp     [rbx+28h], rdi
0x140125aa9  jnz     loc_140125B59
0x140125aaf  mov     rax, [rbx+20h]
0x140125ab3  mov     [r12], rax
0x140125ab7  mov     rcx, [rbx+28h]; HBITMAP
0x140125abb  mov     [r15], rcx
0x140125abe  call    ?ProcessAlphaBitmap@@YAPEAUHBITMAP__@@PEAU1@@Z; ProcessAlphaBitmap(HBITMAP__ *)
0x140125ac3  mov     [rsi+80h], rax
0x140125aca  xor     edx, edx
0x140125acc  mov     rcx, [r12]
0x140125ad0  call    cs:__imp_GreSetBitmapOwner
0x140125ad7  nop     dword ptr [rax+rax+00h]
0x140125adc  mov     rcx, r14
0x140125adf  call    cs:__imp_GreIncQuotaCount
0x140125ae6  nop     dword ptr [rax+rax+00h]
0x140125aeb  mov     rcx, [r15]
0x140125aee  test    rcx, rcx
0x140125af1  jnz     short loc_140125B3A
0x140125af3  mov     rcx, [rsi+80h]
0x140125afa  test    rcx, rcx
0x140125afd  jz      short loc_140125B1C
0x140125aff  xor     edx, edx
0x140125b01  call    cs:__imp_GreSetBitmapOwner
0x140125b08  nop     dword ptr [rax+rax+00h]
0x140125b0d  mov     rcx, r14
0x140125b10  call    cs:__imp_GreIncQuotaCount
0x140125b17  nop     dword ptr [rax+rax+00h]
0x140125b1c  mov     rcx, rsi; struct tagCURSOR *
0x140125b1f  call    ?LinkCursor@@YAXPEAUtagCURSOR@@@Z; LinkCursor(tagCURSOR *)
0x140125b24  mov     al, 1
0x140125b26  add     rsp, 0C0h
0x140125b2d  pop     r15
0x140125b2f  pop     r14
0x140125b31  pop     r13
0x140125b33  pop     r12
0x140125b35  pop     rdi
0x140125b36  pop     rsi
0x140125b37  pop     rbx
0x140125b38  retn
0x140125b3a  xor     edx, edx
0x140125b3c  call    cs:__imp_GreSetBitmapOwner
0x140125b43  nop     dword ptr [rax+rax+00h]
0x140125b48  mov     rcx, r14
0x140125b4b  call    cs:__imp_GreIncQuotaCount
0x140125b52  nop     dword ptr [rax+rax+00h]
0x140125b57  jmp     short loc_140125AF3
0x140125b59  lea     r8, [rsp+0F8h+var_90]
0x140125b5e  mov     r13d, 20h ; ' '
0x140125b64  mov     edx, r13d
0x140125b67  call    GreExtGetObjectW
0x140125b6c  test    eax, eax
0x140125b6e  jz      loc_140125FD2
0x140125b74  lea     r8, [rsp+0F8h+var_70]
0x140125b7c  mov     edx, r13d
0x140125b7f  mov     rcx, [rbx+28h]; HPALETTE
0x140125b83  call    GreExtGetObjectW
0x140125b88  test    eax, eax
0x140125b8a  jz      loc_140125FD2
0x140125b90  mov     eax, dword ptr [rsp+0F8h+var_90+8]
0x140125b94  sar     eax, 1
0x140125b96  mov     ecx, [rsp+0F8h+var_68]
0x140125b9d  cmp     ecx, eax
0x140125b9f  jnz     loc_140125FC8
0x140125ba5  mov     eax, [rsp+0F8h+var_6C]
0x140125bac  cmp     eax, dword ptr [rsp+0F8h+var_90+4]
0x140125bb0  jge     loc_140125AAF
0x140125bb6  jmp     loc_140125FD2
0x140125bbb  mov     rcx, [rbx+20h]
0x140125bbf  call    cs:__imp_GreDeleteObject
0x140125bc6  nop     dword ptr [rax+rax+00h]
0x140125bcb  mov     rcx, [rbx+28h]
0x140125bcf  test    rcx, rcx
0x140125bd2  jnz     loc_140125FB7
0x140125bd8  xor     al, al
0x140125bda  jmp     loc_140125B26
0x140125bdf  lea     rcx, [rsp+0F8h+var_B8]; this
0x140125be4  call    ??0AtomicExecutionCheck@@QEAA@XZ; AtomicExecutionCheck::AtomicExecutionCheck(void)
0x140125be9  nop
0x140125bea  call    cs:__imp_W32GetUserSessionState
0x140125bf1  nop     dword ptr [rax+rax+00h]
0x140125bf6  mov     rcx, [rsp+0F8h+arg_8]
0x140125bfe  mov     r9, [rcx+8]; pszSrc
0x140125c02  add     rax, 0A254h
0x140125c08  mov     [rsp+0F8h+var_A8], rax
0x140125c0d  mov     [rsp+0F8h+var_C8], edi
0x140125c11  mov     [rsp+0F8h+var_C8], edi
0x140125c15  mov     edx, 100h; cchDest
0x140125c1a  mov     rcx, rax; pszDest
0x140125c1d  call    RtlStringCopyWorkerW
0x140125c22  mov     [rsp+0F8h+var_C8], eax
0x140125c26  test    eax, eax
0x140125c28  js      short loc_140125C47
0x140125c2a  xor     edx, edx
0x140125c2c  lea     r8d, [rdx+2]
0x140125c30  mov     rcx, [rsp+0F8h+var_A8]
0x140125c35  call    cs:__imp_UserAddAtomEx
0x140125c3c  nop     dword ptr [rax+rax+00h]
0x140125c41  mov     [rsi+48h], ax
0x140125c45  jmp     short loc_140125C4B
0x140125c47  mov     [rsi+48h], di
0x140125c4b  jmp     short loc_140125C77
0x140125c4d  xor     eax, eax
0x140125c4f  mov     rsi, [rsp+0F8h+arg_0]
0x140125c57  mov     [rsi+48h], ax
0x140125c5b  xor     edi, edi
0x140125c5d  mov     r13b, 8
0x140125c60  mov     rbx, [rsp+0F8h+arg_18]
0x140125c68  mov     r12, [rsp+0F8h+var_A0]
0x140125c6d  mov     r14, [rsp+0F8h+var_98]
0x140125c72  mov     r15d, [rsp+0F8h+var_C4]
0x140125c77  cmp     byte ptr [rsp+0F8h+var_B8], dil
0x140125c7c  jz      short loc_140125C86
0x140125c7e  mov     rax, [rsp+0F8h+var_B0]
0x140125c83  dec     dword ptr [rax+1Ch]
0x140125c86  cmp     [rsi+48h], di
0x140125c8a  jnz     loc_1401259BE
0x140125c90  test    r13b, r15b
0x140125c93  jnz     short loc_140125CBF
0x140125c95  mov     rcx, [rbx+20h]
0x140125c99  test    rcx, rcx
0x140125c9c  jz      short loc_140125CAA
0x140125c9e  call    cs:__imp_GreDeleteObject
0x140125ca5  nop     dword ptr [rax+rax+00h]
0x140125caa  mov     rcx, [rbx+28h]
0x140125cae  test    rcx, rcx
0x140125cb1  jz      short loc_140125CBF
0x140125cb3  call    cs:__imp_GreDeleteObject
0x140125cba  nop     dword ptr [rax+rax+00h]
0x140125cbf  cmp     [r14], di
0x140125cc3  jz      loc_140125BD8
0x140125cc9  mov     rcx, [rsi+40h]
0x140125ccd  call    cs:__imp_Win32FreePool
0x140125cd4  nop     dword ptr [rax+rax+00h]
0x140125cd9  mov     [rsi+40h], rdi
0x140125cdd  mov     [r14], di
0x140125ce1  mov     [rsi+3Ah], di
0x140125ce5  jmp     loc_140125BD8
0x140125cea  mov     dl, 5
0x140125cec  call    cs:__imp_GreReferenceObjectIgnoreOwner
0x140125cf3  nop     dword ptr [rax+rax+00h]
0x140125cf8  test    eax, eax
0x140125cfa  jns     loc_140125A80
0x140125d00  mov     rcx, [rbx+28h]
0x140125d04  call    cs:__imp_GreDeleteObject
0x140125d0b  nop     dword ptr [rax+rax+00h]
0x140125d10  mov     rcx, [rbx+20h]
0x140125d14  jmp     loc_140125FFA
0x140125d19  call    GetDpiForSystem
0x140125d1e  mov     edx, eax
0x140125d20  mov     ecx, 7
0x140125d25  call    GetDpiDependentMetric
0x140125d2a  mov     [rsp+0F8h+arg_28], eax
0x140125d31  mov     rax, [rsp+0F8h+arg_10]
0x140125d39  jmp     loc_14012595F
0x140125d3e  cmp     [rsi+60h], rdi
0x140125d42  jnz     loc_140125BD8
0x140125d48  jmp     loc_14012598A
0x140125d4d  mov     rdx, rax
0x140125d50  mov     rcx, r14
0x140125d53  call    AllocateUnicodeString
0x140125d58  test    eax, eax
0x140125d5a  jnz     loc_1401259AC
0x140125d60  test    r13b, r15b
0x140125d63  jnz     loc_140125CD9
0x140125d69  mov     rcx, [rbx+20h]
0x140125d6d  test    rcx, rcx
0x140125d70  jz      short loc_140125D7E
0x140125d72  call    cs:__imp_GreDeleteObject
0x140125d79  nop     dword ptr [rax+rax+00h]
0x140125d7e  mov     rcx, [rbx+28h]
0x140125d82  test    rcx, rcx
0x140125d85  jz      loc_140125CD9
0x140125d8b  call    cs:__imp_GreDeleteObject
0x140125d92  nop     dword ptr [rax+rax+00h]
0x140125d97  jmp     loc_140125CD9
0x140125d9c  cmp     dword ptr [rsp+0F8h+Size], edi
0x140125da3  jz      short loc_140125DC0
0x140125da5  mov     ecx, dword ptr [rsp+0F8h+Size]
0x140125dac  mov     edx, 75637355h
0x140125db1  call    cs:__imp_Win32AllocPoolWithQuotaZInit
0x140125db8  nop     dword ptr [rax+rax+00h]
0x140125dbd  mov     r9, rax
0x140125dc0  test    r9, r9
0x140125dc3  jnz     loc_1401259CA
0x140125dc9  cmp     [r14], di
0x140125dcd  jz      short loc_140125DEB
0x140125dcf  mov     rcx, [rsi+40h]
0x140125dd3  call    cs:__imp_Win32FreePool
0x140125dda  nop     dword ptr [rax+rax+00h]
0x140125ddf  mov     [rsi+40h], rdi
0x140125de3  mov     [r14], di
0x140125de7  mov     [rsi+3Ah], di
0x140125deb  movzx   ecx, word ptr [rsi+48h]
0x140125def  test    cx, cx
0x140125df2  jz      loc_140125BD8
0x140125df8  call    cs:__imp_UserDeleteAtom
0x140125dff  nop     dword ptr [rax+rax+00h]
0x140125e04  mov     [rsi+48h], di
0x140125e08  jmp     loc_140125BD8
0x140125e0d  movups  xmm0, xmmword ptr [rbx+60h]
0x140125e11  movups  xmmword ptr [r12], xmm0
0x140125e16  movups  xmm1, xmmword ptr [rbx+70h]
  ... truncated ...
```
