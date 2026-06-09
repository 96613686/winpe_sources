# MFETimerProc

- ea: `0x180016d00`
- end: `0x1800172ac`
- name: `MFETimerProc`
- size: `1452`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180003f10`
- `0x18000a670`
- `0x18000aa60`
- `0x180014d2c`
- `0x180015178`
- `0x1800157ec`
- `0x180016d00`
- `0x18001bc4c`
- `0x18001decc`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180016f46`
- `KERNEL32!HeapFree` at `0x180016fab`
- `KERNEL32!HeapFree` at `0x180017229`
- `KERNEL32!HeapFree` at `0x18001724e`
- `KERNEL32!HeapFree` at `0x180016f46`
- `KERNEL32!HeapFree` at `0x180016fab`
- `KERNEL32!HeapFree` at `0x180017229`
- `KERNEL32!HeapFree` at `0x18001724e`

## string_xrefs

- `0x1800170e3`: `MFETimerProc has invalid incoming interface : %x, %x`

## pseudocode

```c
void __fastcall MFETimerProc(unsigned int *a1)
{
  __int64 v2; // r9
  __int64 v3; // r8
  DWORD MostSpecificDestination; // eax
  __int64 v5; // r8
  __int64 v6; // rsi
  __int64 v7; // r14
  int v8; // edi
  DWORD OpaqueInformationPointer; // eax
  _QWORD *v10; // r13
  _QWORD *v11; // r14
  int v12; // r8d
  void *v13; // r8
  _QWORD *v14; // rax
  LPVOID *v15; // rcx
  __int64 v16; // r8
  _QWORD *v17; // rcx
  DWORD v18; // eax
  __int64 v19; // rdi
  __int64 v20; // rdx
  unsigned int v21; // r8d
  __int64 v22; // r9
  const wchar_t *v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // r8
  int v27; // r8d
  void *v28; // r8
  _QWORD *v29; // rax
  LPVOID *v30; // rcx
  unsigned int DestInfoa; // [rsp+20h] [rbp-E0h]
  PRTM_DEST_INFO DestInfo; // [rsp+20h] [rbp-E0h]
  LPVOID *p_lpMem; // [rsp+28h] [rbp-D8h]
  unsigned int v34; // [rsp+28h] [rbp-D8h]
  PVOID OpaqueInfoPointer; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v37; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v38; // [rsp+58h] [rbp-A8h] BYREF
  struct _RTM_DEST_INFO DestHandle; // [rsp+60h] [rbp-A0h] BYREF
  struct _RTM_NET_ADDRESS DestAddress; // [rsp+C0h] [rbp-40h] BYREF
  int v41; // [rsp+E0h] [rbp-20h] BYREF
  char v42[2044]; // [rsp+E4h] [rbp-1Ch] BYREF

  v37 = 0;
  v38 = 0;
  *(_QWORD *)&DestAddress.AddrBits[4] = 0;
  *(_DWORD *)&DestAddress.AddrBits[12] = 0;
  memset_0(&DestHandle, 0, sizeof(DestHandle));
  OpaqueInfoPointer = 0;
  lpMem = 0;
  v41 = 0;
  memset_0(v42, 0, sizeof(v42));
  if ( qword_18002B8A8 )
  {
    v2 = a1[1];
    v3 = *a1;
    v34 = a1[3];
    DestInfoa = a1[2];
    LOWORD(v41) = 0;
    FormatRRASErrorString(&v41, L"ENTERED MFETimerProc, Source : %x %x, Group : %x %x", v3, v2, DestInfoa, v34);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v41);
  }
  *(_DWORD *)DestAddress.AddrBits = *a1;
  *(_DWORD *)&DestAddress.AddressFamily = 2097154;
  MostSpecificDestination = RtmGetMostSpecificDestination(g_hRtmHandle, &DestAddress, 0, 2u, &DestHandle);
  if ( MostSpecificDestination )
  {
    if ( !qword_18002B8A8 )
      goto LABEL_31;
    v5 = *a1;
    LOWORD(v41) = 0;
    FormatRRASErrorString(&v41, L"No Route to source %x, %d", v5, MostSpecificDestination);
    goto LABEL_6;
  }
  v6 = (__int64)DestHandle.DestHandle ^ 0x7754DF32;
  if ( DestHandle.DestHandle != (RTM_DEST_HANDLE)0x7754DF32
    && *(_WORD *)(((__int64)DestHandle.DestHandle ^ 0x7754DF32) + 0x6C) != 1 )
  {
    v7 = v6 + 32;
    v8 = 0;
    AcquireWriteLock(v6 + 32);
    OpaqueInformationPointer = RtmGetOpaqueInformationPointer(g_hRtmHandle, DestHandle.DestHandle, &OpaqueInfoPointer);
    if ( OpaqueInformationPointer )
    {
      if ( qword_18002B8A8 )
      {
        LOWORD(v41) = 0;
        FormatRRASErrorString(&v41, L"Failed to retrieve opaque pointer %x", OpaqueInformationPointer);
        ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v41);
      }
      goto LABEL_23;
    }
    v10 = OpaqueInfoPointer;
    v11 = *(_QWORD **)OpaqueInfoPointer;
    if ( *(_QWORD *)OpaqueInfoPointer )
    {
      AcquireWriteLock(v11 + 2);
      p_lpMem = &lpMem;
      if ( (unsigned int)FindRefEntry((_DWORD)v11, *a1, v12, a1[2]) )
      {
        v13 = lpMem;
        v14 = *(_QWORD **)lpMem;
        if ( *(LPVOID *)(*(_QWORD *)lpMem + 8LL) != lpMem )
          goto LABEL_47;
        v15 = (LPVOID *)*((_QWORD *)lpMem + 1);
        if ( *v15 != lpMem )
          goto LABEL_47;
        *v15 = v14;
        v14[1] = v15;
        HeapFree(hHeap, 0, v13);
      }
      else if ( qword_18002B8A8 )
      {
        v16 = *a1;
        LOWORD(v41) = 0;
        FormatRRASErrorString(&v41, L"Reference does not exist for source %x", v16);
        ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v41);
      }
      v17 = v11 + 2;
      if ( (_QWORD *)*v11 == v11 )
      {
        *v10 = 0;
        ReleaseWriteLock(v17);
        HeapFree(hHeap, 0, v11);
        v7 = v6 + 32;
        v8 = 1;
LABEL_23:
        if ( *(_WORD *)(v6 + 108) == 1 )
        {
          if ( qword_18002B8A8 )
          {
            LOWORD(v41) = 0;
            FormatRRASErrorString(&v41, L"Failed to unlock dest : %x", 6);
            ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v41);
          }
        }
        else
        {
          ReleaseWriteLock(v7);
        }
        if ( v8 )
        {
          v18 = RtmMarkDestForChangeNotification(g_hRtmHandle, g_hNotificationHandle, DestHandle.DestHandle, 0);
          if ( v18 )
          {
            if ( qword_18002B8A8 )
            {
              LOWORD(v41) = 0;
              FormatRRASErrorString(&v41, L"Failed to unmark DEST: %x", v18);
              ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v41);
            }
          }
        }
        goto LABEL_31;
      }
      ReleaseWriteLock(v17);
    }
    v7 = v6 + 32;
    goto LABEL_23;
  }
  if ( qword_18002B8A8 )
  {
    LOWORD(v41) = 0;
    FormatRRASErrorString(&v41, L"Failed to lock dest %x", 6);
LABEL_6:
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v41);
  }
LABEL_31:
  v19 = 32LL * (a1[4] % dword_18002B92C);
  AcquireWriteLock((char *)qword_18002B9E8 + v19 + 16);
  if ( (unsigned int)FindIfEntry((char *)qword_18002B9E8 + v19, a1[4], a1[5], &v37) )
  {
    LookupAndDeleteYourMfe(*a1, v20, a1[2], a1[3], (int)DestInfo, 0, 0, 1);
    p_lpMem = &v38;
    if ( !(unsigned int)FindRefEntry((int)v37 + 56, *a1, v27, a1[2]) )
    {
      if ( !qword_18002B8A8 )
        goto LABEL_44;
      v22 = a1[5];
      v23 = L"MFETimerProc : No reference for interface : %x, %x";
      goto LABEL_34;
    }
    v28 = v38;
    v29 = *(_QWORD **)v38;
    if ( *(LPVOID *)(*(_QWORD *)v38 + 8LL) == v38 )
    {
      v30 = (LPVOID *)*((_QWORD *)v38 + 1);
      if ( *v30 == v38 )
      {
        *v30 = v29;
        v29[1] = v30;
        HeapFree(hHeap, 0, v28);
        goto LABEL_44;
      }
    }
LABEL_47:
    __fastfail(3u);
  }
  if ( !qword_18002B8A8 )
    goto LABEL_44;
  v22 = v21;
  v23 = L"MFETimerProc has invalid incoming interface : %x, %x";
LABEL_34:
  v24 = a1[4];
  LOWORD(v41) = 0;
  FormatRRASErrorString(&v41, v23, v24, v22);
  ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v41);
  if ( qword_18002B8A8 )
  {
    v25 = a1[1];
    v26 = *a1;
    LODWORD(p_lpMem) = a1[3];
    LODWORD(DestInfo) = a1[2];
    LOWORD(v41) = 0;
    FormatRRASErrorString(&v41, L"Source : %x %x, Group : %x %x", v26, v25, DestInfo, p_lpMem);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v41);
  }
LABEL_44:
  ReleaseWriteLock((char *)qword_18002B9E8 + v19 + 16);
  HeapFree(hHeap, 0, a1);
  if ( qword_18002B8A8 )
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(
      gMgmEtwContext,
      qword_18002B8A8,
      L"LEAVING MFETimerProc\n");
}

```

## disassembly

```asm
0x180016d00  mov     [rsp-8+arg_8], rbx
0x180016d05  mov     [rsp-8+arg_10], rsi
0x180016d0a  push    rbp
0x180016d0b  push    rdi
0x180016d0c  push    r12
0x180016d0e  push    r13
0x180016d10  push    r14
0x180016d12  lea     rbp, [rsp-7F0h]
0x180016d1a  sub     rsp, 8F0h
0x180016d21  mov     rax, cs:__security_cookie
0x180016d28  xor     rax, rsp
0x180016d2b  mov     [rbp+810h+var_30], rax
0x180016d32  xor     r12d, r12d
0x180016d35  mov     rbx, rcx
0x180016d38  xor     edx, edx; Val
0x180016d3a  mov     [rsp+910h+var_8C0], r12
0x180016d3f  lea     rcx, [rsp+910h+DestHandle]; void *
0x180016d44  mov     [rsp+910h+var_8B8], r12
0x180016d49  mov     qword ptr [rbp+810h+DestAddress.AddrBits+4], r12
0x180016d4d  lea     r8d, [r12+58h]; Size
0x180016d52  mov     dword ptr [rbp+810h+DestAddress.AddrBits+0Ch], r12d
0x180016d56  call    memset_0
0x180016d5b  xor     edx, edx; Val
0x180016d5d  mov     [rsp+910h+OpaqueInfoPointer], r12
0x180016d62  mov     r8d, 7FCh; Size
0x180016d68  mov     [rsp+910h+lpMem], r12
0x180016d6d  lea     rcx, [rbp+810h+var_82C]; void *
0x180016d71  mov     [rbp+810h+var_830], r12d
0x180016d75  call    memset_0
0x180016d7a  cmp     cs:qword_18002B8A8, r12
0x180016d81  jz      short loc_180016DCB
0x180016d83  mov     eax, [rbx+0Ch]
0x180016d86  lea     rdx, aEnteredMfetime; "ENTERED MFETimerProc, Source : %x %x, G"...
0x180016d8d  mov     r9d, [rbx+4]
0x180016d91  lea     rcx, [rbp+810h+var_830]
0x180016d95  mov     r8d, [rbx]
0x180016d98  mov     dword ptr [rsp+910h+var_8E8], eax
0x180016d9c  mov     eax, [rbx+8]
0x180016d9f  mov     dword ptr [rsp+910h+DestInfo], eax
0x180016da3  mov     word ptr [rbp+810h+var_830], r12w
0x180016da8  call    FormatRRASErrorString
0x180016dad  mov     rdx, cs:qword_18002B8A8
0x180016db4  lea     r8, [rbp+810h+var_830]
0x180016db8  mov     rcx, cs:gMgmEtwContext
0x180016dbf  mov     rax, cs:gMgmTemplateFunc
0x180016dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dcb  mov     eax, [rbx]
0x180016dcd  lea     rdx, [rbp+810h+DestAddress]; DestAddress
0x180016dd1  mov     rcx, cs:g_hRtmHandle; RtmRegHandle
0x180016dd8  mov     r9d, 2; TargetViews
0x180016dde  mov     dword ptr [rbp+810h+DestAddress.AddrBits], eax
0x180016de1  xor     r8d, r8d; ProtocolId
0x180016de4  lea     rax, [rsp+910h+DestHandle]
0x180016de9  mov     dword ptr [rbp+810h+DestAddress.AddressFamily], 200002h
0x180016df0  mov     [rsp+910h+DestInfo], rax; DestInfo
0x180016df5  call    RtmGetMostSpecificDestination
0x180016dfa  mov     r14d, 1
0x180016e00  test    eax, eax
0x180016e02  jz      short loc_180016E4F
0x180016e04  cmp     cs:qword_18002B8A8, r12
0x180016e0b  jz      loc_18001708C
0x180016e11  mov     r8d, [rbx]
0x180016e14  lea     rdx, aNoRouteToSourc_0; "No Route to source %x, %d"
0x180016e1b  mov     r9d, eax
0x180016e1e  mov     word ptr [rbp+810h+var_830], r12w
0x180016e23  lea     rcx, [rbp+810h+var_830]
0x180016e27  call    FormatRRASErrorString
0x180016e2c  mov     rdx, cs:qword_18002B8A8
0x180016e33  lea     r8, [rbp+810h+var_830]
0x180016e37  mov     rcx, cs:gMgmEtwContext
0x180016e3e  mov     rax, cs:gMgmTemplateFunc
0x180016e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e4a  jmp     loc_18001708C
0x180016e4f  mov     rsi, [rsp+910h+DestHandle.DestHandle]
0x180016e54  xor     rsi, 7754DF32h
0x180016e5b  jz      loc_180017174
0x180016e61  cmp     [rsi+6Ch], r14w
0x180016e66  jz      loc_180017174
0x180016e6c  lea     r14, [rsi+20h]
0x180016e70  mov     edi, r12d
0x180016e73  mov     rcx, r14
0x180016e76  call    AcquireWriteLock
0x180016e7b  mov     rdx, [rsp+910h+DestHandle.DestHandle]; DestHandle
0x180016e80  lea     r8, [rsp+910h+OpaqueInfoPointer]; OpaqueInfoPointer
0x180016e85  mov     rcx, cs:g_hRtmHandle; RtmRegHandle
0x180016e8c  call    RtmGetOpaqueInformationPointer
0x180016e91  test    eax, eax
0x180016e93  jz      short loc_180016EDD
0x180016e95  cmp     cs:qword_18002B8A8, r12
0x180016e9c  jz      loc_180016FCD
0x180016ea2  mov     r8d, eax
0x180016ea5  mov     word ptr [rbp+810h+var_830], r12w
0x180016eaa  lea     rdx, aFailedToRetrie; "Failed to retrieve opaque pointer %x"
0x180016eb1  lea     rcx, [rbp+810h+var_830]
0x180016eb5  call    FormatRRASErrorString
0x180016eba  mov     rdx, cs:qword_18002B8A8
0x180016ec1  lea     r8, [rbp+810h+var_830]
0x180016ec5  mov     rcx, cs:gMgmEtwContext
0x180016ecc  mov     rax, cs:gMgmTemplateFunc
0x180016ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ed8  jmp     loc_180016FCD
0x180016edd  mov     r13, [rsp+910h+OpaqueInfoPointer]
0x180016ee2  mov     r14, [r13+0]
0x180016ee6  test    r14, r14
0x180016ee9  jz      loc_180016FC9
0x180016eef  lea     r12, [r14+10h]
0x180016ef3  mov     rcx, r12
0x180016ef6  call    AcquireWriteLock
0x180016efb  mov     edx, [rbx]
0x180016efd  lea     rax, [rsp+910h+lpMem]
0x180016f02  mov     r9d, [rbx+8]
0x180016f06  mov     rcx, r14
0x180016f09  mov     [rsp+910h+var_8E8], rax
0x180016f0e  call    FindRefEntry
0x180016f13  test    eax, eax
0x180016f15  jz      short loc_180016F4E
0x180016f17  mov     r8, [rsp+910h+lpMem]; lpMem
0x180016f1c  mov     rax, [r8]
0x180016f1f  cmp     [rax+8], r8
0x180016f23  jnz     loc_1800172A5
0x180016f29  mov     rcx, [r8+8]
0x180016f2d  cmp     [rcx], r8
0x180016f30  jnz     loc_1800172A5
0x180016f36  mov     [rcx], rax
0x180016f39  xor     edx, edx; dwFlags
0x180016f3b  mov     [rax+8], rcx
0x180016f3f  mov     rcx, cs:hHeap; hHeap
0x180016f46  call    cs:__imp_HeapFree
0x180016f4c  jmp     short loc_180016F8E
0x180016f4e  cmp     cs:qword_18002B8A8, rdi
0x180016f55  jz      short loc_180016F8E
0x180016f57  mov     r8d, [rbx]
0x180016f5a  lea     rdx, aReferenceDoesN; "Reference does not exist for source %x"
0x180016f61  xor     eax, eax
0x180016f63  lea     rcx, [rbp+810h+var_830]
0x180016f67  mov     word ptr [rbp+810h+var_830], ax
0x180016f6b  call    FormatRRASErrorString
0x180016f70  mov     rdx, cs:qword_18002B8A8
0x180016f77  lea     r8, [rbp+810h+var_830]
0x180016f7b  mov     rcx, cs:gMgmEtwContext
0x180016f82  mov     rax, cs:gMgmTemplateFunc
0x180016f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f8e  mov     rcx, r12
0x180016f91  cmp     [r14], r14
0x180016f94  jnz     short loc_180016FC1
0x180016f96  mov     [r13+0], rdi
0x180016f9a  call    ReleaseWriteLock
0x180016f9f  mov     rcx, cs:hHeap; hHeap
0x180016fa6  mov     r8, r14; lpMem
0x180016fa9  xor     edx, edx; dwFlags
0x180016fab  call    cs:__imp_HeapFree
0x180016fb1  mov     eax, 1
0x180016fb6  lea     r14, [rsi+20h]
0x180016fba  mov     edi, eax
0x180016fbc  xor     r12d, r12d
0x180016fbf  jmp     short loc_180016FD2
0x180016fc1  call    ReleaseWriteLock
0x180016fc6  xor     r12d, r12d
0x180016fc9  lea     r14, [rsi+20h]
0x180016fcd  mov     eax, 1
0x180016fd2  cmp     [rsi+6Ch], ax
0x180016fd6  jz      short loc_180016FE2
0x180016fd8  mov     rcx, r14
0x180016fdb  call    ReleaseWriteLock
0x180016fe0  jmp     short loc_180017024
0x180016fe2  cmp     cs:qword_18002B8A8, r12
0x180016fe9  jz      short loc_180017024
0x180016feb  mov     r8d, 6
0x180016ff1  mov     word ptr [rbp+810h+var_830], r12w
0x180016ff6  lea     rdx, aFailedToUnlock; "Failed to unlock dest : %x"
0x180016ffd  lea     rcx, [rbp+810h+var_830]
0x180017001  call    FormatRRASErrorString
0x180017006  mov     rdx, cs:qword_18002B8A8
0x18001700d  lea     r8, [rbp+810h+var_830]
0x180017011  mov     rcx, cs:gMgmEtwContext
0x180017018  mov     rax, cs:gMgmTemplateFunc
0x18001701f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017024  test    edi, edi
0x180017026  jz      short loc_180017086
0x180017028  mov     r8, [rsp+910h+DestHandle.DestHandle]; DestHandle
0x18001702d  xor     r9d, r9d; MarkDest
0x180017030  mov     rdx, cs:g_hNotificationHandle; NotifyHandle
0x180017037  mov     rcx, cs:g_hRtmHandle; RtmRegHandle
0x18001703e  call    RtmMarkDestForChangeNotification
0x180017043  test    eax, eax
0x180017045  jz      short loc_180017086
0x180017047  cmp     cs:qword_18002B8A8, r12
0x18001704e  jz      short loc_180017086
0x180017050  mov     r8d, eax
0x180017053  mov     word ptr [rbp+810h+var_830], r12w
0x180017058  lea     rdx, aFailedToUnmark; "Failed to unmark DEST: %x"
0x18001705f  lea     rcx, [rbp+810h+var_830]
0x180017063  call    FormatRRASErrorString
0x180017068  mov     rdx, cs:qword_18002B8A8
0x18001706f  lea     r8, [rbp+810h+var_830]
0x180017073  mov     rcx, cs:gMgmEtwContext
0x18001707a  mov     rax, cs:gMgmTemplateFunc
0x180017081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017086  mov     r14d, 1
0x18001708c  mov     eax, [rbx+10h]
0x18001708f  xor     edx, edx
0x180017091  div     cs:dword_18002B92C
0x180017097  mov     rcx, cs:qword_18002B9E8
0x18001709e  mov     edi, edx
0x1800170a0  add     rcx, 10h
0x1800170a4  shl     rdi, 5
0x1800170a8  add     rcx, rdi
0x1800170ab  call    AcquireWriteLock
0x1800170b0  mov     rcx, cs:qword_18002B9E8
0x1800170b7  lea     r9, [rsp+910h+var_8C0]
0x1800170bc  mov     edx, [rbx+10h]
0x1800170bf  add     rcx, rdi
0x1800170c2  mov     r8d, [rbx+14h]
0x1800170c6  call    FindIfEntry
0x1800170cb  test    eax, eax
0x1800170cd  jnz     loc_1800171A1
0x1800170d3  cmp     cs:qword_18002B8A8, r12
0x1800170da  jz      loc_18001722F
0x1800170e0  mov     r9d, r8d
0x1800170e3  lea     rdx, aMfetimerprocHa; "MFETimerProc has invalid incoming inter"...
0x1800170ea  mov     r8d, [rbx+10h]
0x1800170ee  lea     rcx, [rbp+810h+var_830]
0x1800170f2  mov     word ptr [rbp+810h+var_830], r12w
0x1800170f7  call    FormatRRASErrorString
0x1800170fc  mov     rdx, cs:qword_18002B8A8
0x180017103  lea     r8, [rbp+810h+var_830]
0x180017107  mov     rcx, cs:gMgmEtwContext
0x18001710e  mov     rax, cs:gMgmTemplateFunc
0x180017115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001711a  cmp     cs:qword_18002B8A8, r12
0x180017121  jz      loc_18001722F
0x180017127  mov     eax, [rbx+0Ch]
0x18001712a  lea     rdx, aSourceXXGroupX; "Source : %x %x, Group : %x %x"
0x180017131  mov     r9d, [rbx+4]
0x180017135  lea     rcx, [rbp+810h+var_830]
0x180017139  mov     r8d, [rbx]
0x18001713c  mov     dword ptr [rsp+910h+var_8E8], eax
0x180017140  mov     eax, [rbx+8]
0x180017143  mov     dword ptr [rsp+910h+DestInfo], eax
0x180017147  mov     word ptr [rbp+810h+var_830], r12w
0x18001714c  call    FormatRRASErrorString
0x180017151  mov     rdx, cs:qword_18002B8A8
0x180017158  lea     r8, [rbp+810h+var_830]
0x18001715c  mov     rcx, cs:gMgmEtwContext
0x180017163  mov     rax, cs:gMgmTemplateFunc
0x18001716a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001716f  jmp     loc_18001722F
0x180017174  cmp     cs:qword_18002B8A8, r12
0x18001717b  jz      loc_18001708C
0x180017181  mov     r8d, 6
0x180017187  mov     word ptr [rbp+810h+var_830], r12w
0x18001718c  lea     rdx, aFailedToLockDe; "Failed to lock dest %x"
0x180017193  lea     rcx, [rbp+810h+var_830]
0x180017197  call    FormatRRASErrorString
0x18001719c  jmp     loc_180016E2C
0x1800171a1  mov     r9d, [rbx+0Ch]
0x1800171a5  mov     r8d, [rbx+8]
0x1800171a9  mov     ecx, [rbx]
0x1800171ab  mov     [rsp+910h+var_8D8], r14d
0x1800171b0  mov     [rsp+910h+var_8E0], r12
0x1800171b5  mov     [rsp+910h+var_8E8], r12
0x1800171ba  call    LookupAndDeleteYourMfe
0x1800171bf  mov     rcx, [rsp+910h+var_8C0]
0x1800171c4  lea     rax, [rsp+910h+var_8B8]
0x1800171c9  mov     edx, [rbx]
0x1800171cb  add     rcx, 38h ; '8'
0x1800171cf  mov     r9d, [rbx+8]
0x1800171d3  mov     [rsp+910h+var_8E8], rax
0x1800171d8  call    FindRefEntry
0x1800171dd  test    eax, eax
0x1800171df  jnz     short loc_1800171FA
0x1800171e1  cmp     cs:qword_18002B8A8, r12
0x1800171e8  jz      short loc_18001722F
0x1800171ea  mov     r9d, [rbx+14h]
0x1800171ee  lea     rdx, aMfetimerprocNo; "MFETimerProc : No reference for interfa"...
0x1800171f5  jmp     loc_1800170EA
0x1800171fa  mov     r8, [rsp+910h+var_8B8]; lpMem
0x1800171ff  mov     rax, [r8]
0x180017202  cmp     [rax+8], r8
0x180017206  jnz     loc_1800172A5
0x18001720c  mov     rcx, [r8+8]
0x180017210  cmp     [rcx], r8
0x180017213  jnz     loc_1800172A5
0x180017219  mov     [rcx], rax
0x18001721c  xor     edx, edx; dwFlags
0x18001721e  mov     [rax+8], rcx
0x180017222  mov     rcx, cs:hHeap; hHeap
0x180017229  call    cs:__imp_HeapFree
0x18001722f  mov     rcx, cs:qword_18002B9E8
0x180017236  add     rcx, 10h
0x18001723a  add     rcx, rdi
0x18001723d  call    ReleaseWriteLock
0x180017242  mov     rcx, cs:hHeap; hHeap
0x180017249  mov     r8, rbx; lpMem
0x18001724c  xor     edx, edx; dwFlags
0x18001724e  call    cs:__imp_HeapFree
0x180017254  mov     rdx, cs:qword_18002B8A8
0x18001725b  test    rdx, rdx
0x18001725e  jz      short loc_18001727A
0x180017260  mov     rcx, cs:gMgmEtwContext
  ... truncated ...
```
