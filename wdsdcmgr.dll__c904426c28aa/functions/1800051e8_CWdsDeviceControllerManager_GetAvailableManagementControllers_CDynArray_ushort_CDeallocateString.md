# CWdsDeviceControllerManager::GetAvailableManagementControllers(CDynArray<ushort *,CDeallocateString> *)

- ea: `0x1800051e8`
- end: `0x180005428`
- name: `?GetAvailableManagementControllers@CWdsDeviceControllerManager@@QEAAKPEAV?$CDynArray@PEAGVCDeallocateString@@@@@Z`
- size: `576`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002bd8`

## callees

- `0x180004f98`
- `0x1800051e8`
- `0x180006ab0`
- `0x180007310`
- `0x180012f34`
- `0x180013254`
- `0x180013dcc`
- `0x180014d58`
- `0x1800150b8`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180005336`
- `KERNEL32!EnterCriticalSection` at `0x180005336`
- `KERNEL32!LeaveCriticalSection` at `0x180005406`
- `KERNEL32!LeaveCriticalSection` at `0x180005406`
- `KERNEL32!GetCurrentThreadId` at `0x180005326`
- `KERNEL32!GetCurrentThreadId` at `0x180005326`
- `KERNEL32!ReleaseSemaphore` at `0x1800053dd`
- `KERNEL32!ReleaseSemaphore` at `0x1800053dd`

## string_xrefs

- `0x180005358`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180005393`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x1800053f7`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x1800053eb`: `ReleaseSemaphore(m_hReaderDone, 1, 0)`
- `0x18000534c`: `m_ActiveWriter.m_uNestedReaders > 0`
- `0x180005387`: `GetReaderSlot(uThreadId, &uIndex) == 0L`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerManager::GetAvailableManagementControllers(__int64 a1, __int64 a2)
{
  signed int v3; // edi
  const char *v5; // rdx
  CWdsDeviceControllerManager *v6; // rcx
  unsigned __int16 *v7; // rbx
  __int64 v8; // rsi
  __int64 v9; // r14
  const char *v10; // rdx
  unsigned int v11; // eax
  const char *v12; // rdx
  unsigned int v13; // eax
  unsigned int v14; // esi
  DWORD CurrentThreadId; // eax
  LPCRITICAL_SECTION v16; // rbx
  unsigned int v17; // ebp
  int v18; // r9d
  int SpinCount_high; // eax
  __int64 v20; // rcx
  _DWORD *OwningThread; // rdx
  int v22; // eax
  bool v23; // zf
  int v24; // r9d
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+40h] [rbp-28h] BYREF
  int v27; // [rsp+48h] [rbp-20h]
  unsigned __int16 *i; // [rsp+70h] [rbp+8h] BYREF

  lpCriticalSection = (LPCRITICAL_SECTION)(a1 + 40);
  v3 = 0;
  v27 = 0;
  CAutoReaderLock::Lock((CAutoReaderLock *)&lpCriticalSection);
  v7 = 0;
  v8 = 0;
  for ( i = 0; (unsigned int)v8 < *(_DWORD *)(a1 + 196); i = 0 )
  {
    v9 = 0;
    v3 = 0;
    if ( (unsigned int)v8 < *(_DWORD *)(a1 + 196) )
      v9 = *(_QWORD *)(*(_QWORD *)(a1 + 184) + 8 * v8);
    else
      v3 = 1413;
    if ( ElValidateWin32(v3, v5, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x874u) )
      break;
    v3 = DuplicateStringW(*(const unsigned __int16 **)(*(_QWORD *)(v9 + 8) + 8LL), &i);
    v11 = ElValidateWin32(v3, v10, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x878u);
    v7 = i;
    if ( v11 )
      break;
    v3 = CDynArray<CWdsDeviceControllerManager::CQueryEntry *,CDeallocateNone>::AddItem(a2, i);
    if ( ElValidateWin32(v3, v12, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x87Bu) )
      break;
    v7 = 0;
    v8 = (unsigned int)(v8 + 1);
  }
  v13 = (unsigned __int16)v3 | 0x80070000;
  if ( v3 <= 0 )
    v13 = v3;
  CWdsDeviceControllerManager::LogDeviceManagement(v6, 3u, 0, 0, 0, *(_DWORD *)(a2 + 12), v13);
  if ( v7 )
    operator delete(v7);
  if ( v27 == 1 )
  {
    v14 = 0;
    CurrentThreadId = GetCurrentThreadId();
    v16 = lpCriticalSection;
    v17 = CurrentThreadId;
    EnterCriticalSection(lpCriticalSection);
    if ( LODWORD(v16[1].SpinCount) == v17 )
    {
      SpinCount_high = HIDWORD(v16[1].SpinCount);
      if ( !SpinCount_high )
      {
        WdsAssert(
          "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
          0x22Eu,
          "m_ActiveWriter.m_uNestedReaders > 0",
          v18,
          0);
        SpinCount_high = HIDWORD(v16[1].SpinCount);
      }
      HIDWORD(v16[1].SpinCount) = SpinCount_high - 1;
    }
    else
    {
      v20 = 0;
      while ( *((_DWORD *)v16[2].OwningThread + 2 * v20) != v17 )
      {
        v20 = (unsigned int)(v20 + 1);
        if ( (unsigned int)v20 > v16[2].LockCount )
        {
          WdsAssert(
            "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
            0x236u,
            "GetReaderSlot(uThreadId, &uIndex) == 0L",
            v18,
            0);
          goto LABEL_23;
        }
      }
      v14 = v20;
LABEL_23:
      OwningThread = v16[2].OwningThread;
      v22 = OwningThread[2 * v14 + 1];
      if ( v22 )
      {
        OwningThread[2 * v14 + 1] = v22 - 1;
      }
      else
      {
        CMRSWLock::FreeReaderSlot((CMRSWLock *)v16, v17, v14);
        v23 = LODWORD(v16[2].LockSemaphore)-- == 1;
        if ( v23 && LODWORD(v16[2].SpinCount) && !ReleaseSemaphore(v16[1].OwningThread, 1, 0) )
          WdsAssert(
            "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
            0x251u,
            "ReleaseSemaphore(m_hReaderDone, 1, 0)",
            v24,
            0);
      }
    }
    LeaveCriticalSection(v16);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800051e8  mov     r11, rsp
0x1800051eb  mov     [r11+10h], rbx
0x1800051ef  mov     [r11+18h], rbp
0x1800051f3  mov     [r11+20h], rsi
0x1800051f7  push    rdi
0x1800051f8  push    r14
0x1800051fa  push    r15
0x1800051fc  sub     rsp, 50h
0x180005200  lea     rax, [rcx+28h]
0x180005204  mov     rbp, rcx
0x180005207  mov     [r11-28h], rax
0x18000520b  lea     rcx, [r11-28h]; this
0x18000520f  xor     edi, edi
0x180005211  mov     r15, rdx
0x180005214  and     [rsp+68h+var_20], edi
0x180005218  call    ?Lock@CAutoReaderLock@@QEAAXXZ; CAutoReaderLock::Lock(void)
0x18000521d  xor     ebx, ebx
0x18000521f  xor     esi, esi
0x180005221  mov     [rsp+68h+arg_0], rbx
0x180005226  cmp     [rbp+0C4h], ebx
0x18000522c  jbe     loc_1800052D4
0x180005232  xor     r14d, r14d
0x180005235  xor     edi, edi
0x180005237  cmp     esi, [rbp+0C4h]
0x18000523d  jb      short loc_180005246
0x18000523f  mov     edi, 585h
0x180005244  jmp     short loc_180005251
0x180005246  mov     rax, [rbp+0B8h]
0x18000524d  mov     r14, [rax+rsi*8]
0x180005251  mov     r9d, 874h; unsigned int
0x180005257  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x18000525e  mov     ecx, edi; unsigned int
0x180005260  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005265  test    eax, eax
0x180005267  jnz     short loc_1800052D4
0x180005269  mov     rcx, [r14+8]
0x18000526d  lea     rdx, [rsp+68h+arg_0]; unsigned __int16 **
0x180005272  mov     rcx, [rcx+8]; unsigned __int16 *
0x180005276  call    ?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x18000527b  mov     r9d, 878h; unsigned int
0x180005281  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180005288  mov     ecx, eax; unsigned int
0x18000528a  mov     edi, eax
0x18000528c  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005291  mov     rbx, [rsp+68h+arg_0]
0x180005296  test    eax, eax
0x180005298  jnz     short loc_1800052D4
0x18000529a  mov     rdx, rbx
0x18000529d  mov     rcx, r15
0x1800052a0  call    ?AddItem@?$CDynArray@PEAUCQueryEntry@CWdsDeviceControllerManager@@VCDeallocateNone@@@@QEAAKPEAUCQueryEntry@CWdsDeviceControllerManager@@@Z; CDynArray<CWdsDeviceControllerManager::CQueryEntry *,CDeallocateNone>::AddItem(CWdsDeviceControllerManager::CQueryEntry *)
0x1800052a5  mov     r9d, 87Bh; unsigned int
0x1800052ab  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800052b2  mov     ecx, eax; unsigned int
0x1800052b4  mov     edi, eax
0x1800052b6  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800052bb  test    eax, eax
0x1800052bd  jnz     short loc_1800052D4
0x1800052bf  xor     ebx, ebx
0x1800052c1  inc     esi
0x1800052c3  mov     [rsp+68h+arg_0], rbx
0x1800052c8  cmp     esi, [rbp+0C4h]
0x1800052ce  jb      loc_180005232
0x1800052d4  movzx   eax, di
0x1800052d7  or      eax, 80070000h
0x1800052dc  test    edi, edi
0x1800052de  cmovle  eax, edi
0x1800052e1  xor     r9d, r9d; unsigned __int16 *
0x1800052e4  mov     [rsp+68h+var_38], eax; int
0x1800052e8  xor     r8d, r8d; unsigned __int16 *
0x1800052eb  mov     eax, [r15+0Ch]
0x1800052ef  mov     [rsp+68h+var_40], eax; unsigned int
0x1800052f3  and     [rsp+68h+var_48], 0
0x1800052f9  lea     edx, [r9+3]; unsigned int
0x1800052fd  call    ?LogDeviceManagement@CWdsDeviceControllerManager@@AEAAXKPEBG0PEAVCWdsComMetadataBuilder@@KJ@Z; CWdsDeviceControllerManager::LogDeviceManagement(ulong,ushort const *,ushort const *,CWdsComMetadataBuilder *,ulong,long)
0x180005302  test    rbx, rbx
0x180005305  jz      short loc_18000530F
0x180005307  mov     rcx, rbx; Block
0x18000530a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000530f  mov     eax, [rsp+68h+var_20]
0x180005313  test    eax, eax
0x180005315  jz      loc_18000540C
0x18000531b  cmp     eax, 1
0x18000531e  jnz     loc_18000540C
0x180005324  xor     esi, esi
0x180005326  call    cs:__imp_GetCurrentThreadId
0x18000532c  mov     rbx, [rsp+68h+lpCriticalSection]
0x180005331  mov     ebp, eax
0x180005333  mov     rcx, rbx; lpCriticalSection
0x180005336  call    cs:__imp_EnterCriticalSection
0x18000533c  cmp     [rbx+48h], ebp
0x18000533f  jnz     short loc_180005371
0x180005341  mov     eax, [rbx+4Ch]
0x180005344  test    eax, eax
0x180005346  jnz     short loc_180005367
0x180005348  and     dword ptr [rsp+68h+var_48], esi
0x18000534c  lea     r8, aMActivewriterM_1; "m_ActiveWriter.m_uNestedReaders > 0"
0x180005353  mov     edx, 22Eh; unsigned int
0x180005358  lea     rcx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18000535f  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180005364  mov     eax, [rbx+4Ch]
0x180005367  dec     eax
0x180005369  mov     [rbx+4Ch], eax
0x18000536c  jmp     loc_180005403
0x180005371  mov     rdx, [rbx+60h]
0x180005375  xor     ecx, ecx
0x180005377  cmp     [rdx+rcx*8], ebp
0x18000537a  jz      short loc_1800053A1
0x18000537c  inc     ecx
0x18000537e  cmp     ecx, [rbx+58h]
0x180005381  jbe     short loc_180005377
0x180005383  and     dword ptr [rsp+68h+var_48], esi
0x180005387  lea     r8, aGetreaderslotU; "GetReaderSlot(uThreadId, &uIndex) == 0L"
0x18000538e  mov     edx, 236h; unsigned int
0x180005393  lea     rcx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18000539a  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000539f  jmp     short loc_1800053A3
0x1800053a1  mov     esi, ecx
0x1800053a3  mov     rdx, [rbx+60h]
0x1800053a7  mov     ecx, esi
0x1800053a9  mov     eax, [rdx+rcx*8+4]
0x1800053ad  test    eax, eax
0x1800053af  jz      short loc_1800053B9
0x1800053b1  dec     eax
0x1800053b3  mov     [rdx+rcx*8+4], eax
0x1800053b7  jmp     short loc_180005403
0x1800053b9  mov     r8d, esi; unsigned int
0x1800053bc  mov     edx, ebp; unsigned int
0x1800053be  mov     rcx, rbx; this
0x1800053c1  call    ?FreeReaderSlot@CMRSWLock@@AEAAXKK@Z; CMRSWLock::FreeReaderSlot(ulong,ulong)
0x1800053c6  add     dword ptr [rbx+68h], 0FFFFFFFFh
0x1800053ca  jnz     short loc_180005403
0x1800053cc  cmp     dword ptr [rbx+70h], 0
0x1800053d0  jbe     short loc_180005403
0x1800053d2  mov     rcx, [rbx+38h]; hSemaphore
0x1800053d6  xor     r8d, r8d; lpPreviousCount
0x1800053d9  lea     edx, [r8+1]; lReleaseCount
0x1800053dd  call    cs:__imp_ReleaseSemaphore
0x1800053e3  test    eax, eax
0x1800053e5  jnz     short loc_180005403
0x1800053e7  and     dword ptr [rsp+68h+var_48], eax
0x1800053eb  lea     r8, aReleasesemapho_0; "ReleaseSemaphore(m_hReaderDone, 1, 0)"
0x1800053f2  mov     edx, 251h; unsigned int
0x1800053f7  lea     rcx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800053fe  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180005403  mov     rcx, rbx; lpCriticalSection
0x180005406  call    cs:__imp_LeaveCriticalSection
0x18000540c  lea     r11, [rsp+68h+var_18]
0x180005411  mov     eax, edi
0x180005413  mov     rbx, [r11+28h]
0x180005417  mov     rbp, [r11+30h]
0x18000541b  mov     rsi, [r11+38h]
0x18000541f  mov     rsp, r11
0x180005422  pop     r15
0x180005424  pop     r14
0x180005426  pop     rdi
0x180005427  retn
```
