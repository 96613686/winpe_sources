# WDiagProcessAcmStateTransition(_WD_INTERFACE_CONTEXT *,void *,_ACE_STATE_MACHINE *,void *,ulong,ulong,unsigned __int64,ulong)

- ea: `0x180011d68`
- end: `0x180012264`
- name: `?WDiagProcessAcmStateTransition@@YAKPEAU_WD_INTERFACE_CONTEXT@@PEAXPEAU_ACE_STATE_MACHINE@@1KK_KK@Z`
- size: `1276`
- prototype: `unsigned int __usercall@<eax>(struct _WD_INTERFACE_CONTEXT *@<rcx>, void *@<rdx>, struct _ACE_STATE_MACHINE *@<r8>, void *@<r9>, unsigned int, unsigned int, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180011558`

## callees

- `0x180011530`
- `0x180011d68`
- `0x18001d5b4`
- `0x1800469dc`
- `0x1800766d0`
- `0x1801c81ac`
- `0x1801c82e4`
- `0x1801ce644`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011e4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011f3d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011e4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011f3d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011de0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011ed3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011de0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011ed3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011ded`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011ee0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011ded`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011ee0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011dd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011ec7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012085`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012210`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011dd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011ec7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012085`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012210`

## pseudocode

```c
__int64 __fastcall WDiagProcessAcmStateTransition(
        struct _WD_INTERFACE_CONTEXT *a1,
        void *a2,
        struct _ACE_STATE_MACHINE *a3,
        void *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned __int64 a7,
        unsigned int a8)
{
  PVOID *v11; // r11
  DWORD CurrentThreadId; // esi
  int v13; // r9d
  DWORD v14; // esi
  unsigned int v15; // ebx
  char v17; // al
  __int64 v18; // r11
  char v19; // al
  int v20; // [rsp+28h] [rbp-80h]

  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 68, &WPP_fec73b95d5a537674450248f38664378_Traceguids);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a4 )
  {
    CurrentThreadId = GetCurrentThreadId();
    EnterCriticalSection((LPCRITICAL_SECTION)a1 + 84);
    WaitForSingleObject(*((HANDLE *)a1 + 430), 0xFFFFFFFF);
    if ( (*((_BYTE *)a1 + 3448) & 4) != 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
    {
      WPP_SF_qqdsddsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (_BYTE)a1 + 24,
        *((_DWORD *)a1 + 864),
        *((_QWORD *)a1 + 433),
        *((_DWORD *)a1 + 865),
        CurrentThreadId,
        (__int64)"WDiagProcessAcmStateTransition",
        240);
    }
    *((_DWORD *)a1 + 862) |= 4u;
    *((_DWORD *)a1 + 864) = CurrentThreadId;
    *((_DWORD *)a1 + 865) = 1264;
    *((_QWORD *)a1 + 433) = "WDiagProcessAcmStateTransition";
    *((_DWORD *)a1 + 1010) = a5;
    if ( (*((_BYTE *)a1 + 3448) & 4) == 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
    {
      v17 = GetCurrentThreadId();
      WPP_SF_qqDsdDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (_BYTE)a1 + 24,
        v20,
        *((_QWORD *)a1 + 435),
        *((_DWORD *)a1 + 868),
        v17,
        (__int64)"WDiagProcessAcmStateTransition",
        242);
    }
    *((_DWORD *)a1 + 862) &= ~4u;
    *((_DWORD *)a1 + 868) = 1266;
    *((_QWORD *)a1 + 435) = "WDiagProcessAcmStateTransition";
    *((_DWORD *)a1 + 864) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)a1 + 84);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  v13 = *((_DWORD *)a3 + 16);
  if ( !v13 )
  {
    if ( v11 != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)v11 + 57) & 0x200) != 0 )
      {
        WPP_SF_(v11[27], 60, &WPP_fec73b95d5a537674450248f38664378_Traceguids);
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v11 != &WPP_GLOBAL_Control && *((_BYTE *)v11 + 225) >= 4u && (*((_BYTE *)v11 + 228) & 4) != 0 )
      {
        AceTriggerToName(a7);
        WPP_SF_SSS(*(_QWORD *)(v18 + 216), (__int64)(&g_strStateName)[a6], (__int64)(&g_strStateName)[a8]);
      }
    }
    v14 = GetCurrentThreadId();
    EnterCriticalSection((LPCRITICAL_SECTION)a1 + 84);
    WaitForSingleObject(*((HANDLE *)a1 + 430), 0xFFFFFFFF);
    if ( (*((_BYTE *)a1 + 3448) & 4) != 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
    {
      WPP_SF_qqdsddsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (_BYTE)a1 + 24,
        *((_DWORD *)a1 + 864),
        *((_QWORD *)a1 + 433),
        *((_DWORD *)a1 + 865),
        v14,
        (__int64)"WDiagProcessAcmScanSMTransition",
        243);
    }
    *((_DWORD *)a1 + 862) |= 4u;
    *((_DWORD *)a1 + 864) = v14;
    *((_DWORD *)a1 + 865) = 1011;
    *((_QWORD *)a1 + 433) = "WDiagProcessAcmScanSMTransition";
    *((_DWORD *)a1 + 28) = a6;
    *((_DWORD *)a1 + 29) = a8;
    *((_QWORD *)a1 + 15) = a7;
    if ( (*((_BYTE *)a1 + 3448) & 4) == 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
    {
      v19 = GetCurrentThreadId();
      WPP_SF_qqDsdDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (_BYTE)a1 + 24,
        v20,
        *((_QWORD *)a1 + 435),
        *((_DWORD *)a1 + 868),
        v19,
        (__int64)"WDiagProcessAcmScanSMTransition",
        247);
    }
    *((_DWORD *)a1 + 862) &= ~4u;
    *((_DWORD *)a1 + 868) = 1015;
    *((_QWORD *)a1 + 435) = "WDiagProcessAcmScanSMTransition";
    *((_DWORD *)a1 + 864) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)a1 + 84);
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 62, &WPP_fec73b95d5a537674450248f38664378_Traceguids);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    v15 = 0;
    goto LABEL_20;
  }
  if ( v13 == 1 )
  {
    v15 = WDiagProcessAcmConnectSMTransition(a1, a6, a8, a7);
LABEL_26:
    v11 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_20;
  }
  v15 = 0;
  if ( v11 == &WPP_GLOBAL_Control )
    return v15;
  if ( *((_BYTE *)v11 + 225) && (*((_BYTE *)v11 + 228) & 4) != 0 )
  {
    WPP_SF_didd(v11[27], a2);
    goto LABEL_26;
  }
LABEL_20:
  if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 57) & 0x200) != 0 )
    WPP_SF_(v11[27], 70, &WPP_fec73b95d5a537674450248f38664378_Traceguids);
  return v15;
}

```

## disassembly

```asm
0x180011d68  push    rbx
0x180011d6a  push    rbp
0x180011d6b  push    rsi
0x180011d6c  push    rdi
0x180011d6d  push    r12
0x180011d6f  push    r13
0x180011d71  push    r14
0x180011d73  push    r15
0x180011d75  sub     rsp, 68h
0x180011d79  mov     rbx, r9
0x180011d7c  mov     r14, r8
0x180011d7f  mov     rdi, rcx
0x180011d82  mov     r11, cs:WPP_GLOBAL_Control
0x180011d89  lea     r13, WPP_GLOBAL_Control
0x180011d90  cmp     r11, r13
0x180011d93  jz      short loc_180011DC1
0x180011d95  test    dword ptr [r11+0E4h], 200h
0x180011da0  jz      short loc_180011DC1
0x180011da2  mov     rcx, [r11+0D8h]
0x180011da9  lea     r8, WPP_fec73b95d5a537674450248f38664378_Traceguids
0x180011db0  mov     edx, 44h ; 'D'
0x180011db5  call    WPP_SF_
0x180011dba  mov     r11, cs:WPP_GLOBAL_Control
0x180011dc1  mov     r15b, 1
0x180011dc4  test    rbx, rbx
0x180011dc7  jz      loc_180011E58
0x180011dcd  lea     rbx, [rdi+0D18h]
0x180011dd4  call    cs:__imp_GetCurrentThreadId
0x180011dda  lea     rcx, [rbx+8]; lpCriticalSection
0x180011dde  mov     esi, eax
0x180011de0  call    cs:__imp_EnterCriticalSection
0x180011de6  mov     rcx, [rbx+58h]; hHandle
0x180011dea  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180011ded  call    cs:__imp_WaitForSingleObject
0x180011df3  test    byte ptr [rbx+60h], 4
0x180011df7  lea     r12, aWdiagprocessac_3; "WDiagProcessAcmStateTransition"
0x180011dfe  jnz     loc_180011FF0
0x180011e04  or      dword ptr [rbx+60h], 4
0x180011e08  mov     eax, [rsp+0A8h+arg_20]
0x180011e0f  mov     [rbx+68h], esi
0x180011e12  mov     esi, 4F2h
0x180011e17  mov     dword ptr [rbx+6Ch], 4F0h
0x180011e1e  mov     [rbx+70h], r12
0x180011e22  mov     [rdi+0FC8h], eax
0x180011e28  test    byte ptr [rbx+60h], 4
0x180011e2c  jz      loc_18001205B
0x180011e32  and     dword ptr [rbx+60h], 0FFFFFFFBh
0x180011e36  lea     rcx, [rbx+8]; lpCriticalSection
0x180011e3a  mov     [rbx+78h], esi
0x180011e3d  mov     [rbx+80h], r12
0x180011e44  mov     dword ptr [rbx+68h], 0
0x180011e4b  call    cs:__imp_LeaveCriticalSection
0x180011e51  mov     r11, cs:WPP_GLOBAL_Control
0x180011e58  mov     r9d, [r14+40h]
0x180011e5c  test    r9d, r9d
0x180011e5f  jnz     loc_180011FBC
0x180011e65  mov     r14d, [rsp+0A8h+arg_38]
0x180011e6d  mov     r15, [rsp+0A8h+arg_30]
0x180011e75  mov     r12d, [rsp+0A8h+arg_28]
0x180011e7d  cmp     r11, r13
0x180011e80  jz      short loc_180011EC0
0x180011e82  test    dword ptr [r11+0E4h], 200h
0x180011e8d  jz      short loc_180011EAD
0x180011e8f  mov     rcx, [r11+0D8h]
0x180011e96  lea     edx, [r9+3Ch]
0x180011e9a  lea     r8, WPP_fec73b95d5a537674450248f38664378_Traceguids
0x180011ea1  call    WPP_SF_
0x180011ea6  mov     r11, cs:WPP_GLOBAL_Control
0x180011ead  cmp     r11, r13
0x180011eb0  jz      short loc_180011EC0
0x180011eb2  cmp     byte ptr [r11+0E1h], 4
0x180011eba  jnb     loc_180012125
0x180011ec0  lea     rbx, [rdi+0D18h]
0x180011ec7  call    cs:__imp_GetCurrentThreadId
0x180011ecd  lea     rcx, [rbx+8]; lpCriticalSection
0x180011ed1  mov     esi, eax
0x180011ed3  call    cs:__imp_EnterCriticalSection
0x180011ed9  mov     rcx, [rbx+58h]; hHandle
0x180011edd  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180011ee0  call    cs:__imp_WaitForSingleObject
0x180011ee6  test    byte ptr [rbx+60h], 4
0x180011eea  lea     rdx, aWdiagprocessac_4; "WDiagProcessAcmScanSMTransition"
0x180011ef1  jnz     loc_180012174
0x180011ef7  or      dword ptr [rbx+60h], 4
0x180011efb  mov     [rbx+68h], esi
0x180011efe  mov     esi, 3F7h
0x180011f03  mov     dword ptr [rbx+6Ch], 3F3h
0x180011f0a  mov     [rbx+70h], rdx
0x180011f0e  mov     [rdi+70h], r12d
0x180011f12  mov     [rdi+74h], r14d
0x180011f16  mov     [rdi+78h], r15
0x180011f1a  test    byte ptr [rbx+60h], 4
0x180011f1e  jz      loc_1800121E6
0x180011f24  and     dword ptr [rbx+60h], 0FFFFFFFBh
0x180011f28  lea     rcx, [rbx+8]; lpCriticalSection
0x180011f2c  mov     [rbx+78h], esi
0x180011f2f  mov     [rbx+80h], rdx
0x180011f36  mov     dword ptr [rbx+68h], 0
0x180011f3d  call    cs:__imp_LeaveCriticalSection
0x180011f43  mov     r11, cs:WPP_GLOBAL_Control
0x180011f4a  cmp     r11, r13
0x180011f4d  jz      short loc_180011F7B
0x180011f4f  test    dword ptr [r11+0E4h], 200h
0x180011f5a  jz      short loc_180011F7B
0x180011f5c  mov     rcx, [r11+0D8h]
0x180011f63  lea     r8, WPP_fec73b95d5a537674450248f38664378_Traceguids
0x180011f6a  mov     edx, 3Eh ; '>'
0x180011f6f  call    WPP_SF_
0x180011f74  mov     r11, cs:WPP_GLOBAL_Control
0x180011f7b  xor     ebx, ebx
0x180011f7d  cmp     r11, r13
0x180011f80  jnz     short loc_180011F95
0x180011f82  mov     eax, ebx
0x180011f84  add     rsp, 68h
0x180011f88  pop     r15
0x180011f8a  pop     r14
0x180011f8c  pop     r13
0x180011f8e  pop     r12
0x180011f90  pop     rdi
0x180011f91  pop     rsi
0x180011f92  pop     rbp
0x180011f93  pop     rbx
0x180011f94  retn
0x180011f95  test    dword ptr [r11+0E4h], 200h
0x180011fa0  jz      short loc_180011F82
0x180011fa2  mov     rcx, [r11+0D8h]
0x180011fa9  lea     r8, WPP_fec73b95d5a537674450248f38664378_Traceguids
0x180011fb0  mov     edx, 46h ; 'F'
0x180011fb5  call    WPP_SF_
0x180011fba  jmp     short loc_180011F82
0x180011fbc  cmp     r9d, 1
0x180011fc0  jnz     loc_1800120CB
0x180011fc6  mov     r9, [rsp+0A8h+arg_30]; unsigned __int64
0x180011fce  mov     rcx, rdi; struct _WD_INTERFACE_CONTEXT *
0x180011fd1  mov     r8d, [rsp+0A8h+arg_38]; unsigned int
0x180011fd9  mov     edx, [rsp+0A8h+arg_28]; unsigned int
0x180011fe0  call    ?WDiagProcessAcmConnectSMTransition@@YAKPEAU_WD_INTERFACE_CONTEXT@@KK_K@Z; WDiagProcessAcmConnectSMTransition(_WD_INTERFACE_CONTEXT *,ulong,ulong,unsigned __int64)
0x180011fe5  mov     ebx, eax
0x180011fe7  mov     r11, cs:WPP_GLOBAL_Control
0x180011fee  jmp     short loc_180011F7D
0x180011ff0  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ff7  cmp     rcx, r13
0x180011ffa  jz      loc_180011E04
0x180012000  cmp     [rcx+0E1h], r15b
0x180012007  jb      loc_180011E04
0x18001200d  test    byte ptr [rcx+0E4h], 40h
0x180012014  jz      loc_180011E04
0x18001201a  mov     eax, [rbx+6Ch]
0x18001201d  mov     r9, rdi
0x180012020  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180012027  mov     dword ptr [rsp+0A8h+var_58], 4F0h; char
0x18001202f  mov     [rsp+0A8h+var_60], r12; __int64
0x180012034  mov     dword ptr [rsp+0A8h+var_68], esi; char
0x180012038  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x18001203c  mov     rax, [rbx+70h]
0x180012040  mov     [rsp+0A8h+var_78], rax; __int64
0x180012045  mov     eax, [rbx+68h]
0x180012048  mov     dword ptr [rsp+0A8h+var_80], eax; char
0x18001204c  mov     qword ptr [rsp+0A8h+var_88], rbx; char
0x180012051  call    WPP_SF_qqdsddsd
0x180012056  jmp     loc_180011E04
0x18001205b  mov     rax, cs:WPP_GLOBAL_Control
0x180012062  cmp     rax, r13
0x180012065  jz      loc_180011E32
0x18001206b  cmp     [rax+0E1h], r15b
0x180012072  jb      loc_180011E32
0x180012078  test    byte ptr [rax+0E4h], 40h
0x18001207f  jz      loc_180011E32
0x180012085  call    cs:__imp_GetCurrentThreadId
0x18001208b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012092  mov     r9, rdi
0x180012095  mov     dword ptr [rsp+0A8h+var_58], esi; char
0x180012099  mov     [rsp+0A8h+var_60], r12; __int64
0x18001209e  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x1800120a2  mov     eax, [rbx+78h]
0x1800120a5  mov     rcx, [rcx+0D8h]; LoggerHandle
0x1800120ac  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x1800120b0  mov     rax, [rbx+80h]
0x1800120b7  mov     [rsp+0A8h+var_78], rax; __int64
0x1800120bc  mov     qword ptr [rsp+0A8h+var_88], rbx; char
0x1800120c1  call    WPP_SF_qqDsdDsd
0x1800120c6  jmp     loc_180011E32
0x1800120cb  xor     ebx, ebx
0x1800120cd  cmp     r11, r13
0x1800120d0  jz      loc_180011F82
0x1800120d6  cmp     [r11+0E1h], r15b
0x1800120dd  jb      loc_180011F7D
0x1800120e3  test    byte ptr [r11+0E4h], 4
0x1800120eb  jz      loc_180011F7D
0x1800120f1  mov     eax, [rsp+0A8h+arg_38]
0x1800120f8  mov     rcx, [r11+0D8h]
0x1800120ff  mov     dword ptr [rsp+0A8h+var_78], eax
0x180012103  mov     eax, [rsp+0A8h+arg_28]
0x18001210a  mov     dword ptr [rsp+0A8h+var_80], eax
0x18001210e  mov     rax, [rsp+0A8h+arg_30]
0x180012116  mov     qword ptr [rsp+0A8h+var_88], rax
0x18001211b  call    WPP_SF_didd
0x180012120  jmp     loc_180011FE7
0x180012125  test    byte ptr [r11+0E4h], 4
0x18001212d  jz      loc_180011EC0
0x180012133  mov     rcx, r15; unsigned __int64
0x180012136  lea     rbx, ?g_strStateName@@3QBQEBGB; ushort const * const near * const g_strStateName
0x18001213d  call    ?AceTriggerToName@@YAPEBG_K@Z; AceTriggerToName(unsigned __int64)
0x180012142  mov     rcx, [r11+0D8h]; LoggerHandle
0x180012149  lea     r8, WPP_fec73b95d5a537674450248f38664378_Traceguids
0x180012150  mov     r9, rax
0x180012153  mov     edx, 3Dh ; '='
0x180012158  mov     rax, [rbx+r14*8]
0x18001215c  mov     qword ptr [rsp+0A8h+var_80], rax; __int64
0x180012161  mov     rax, [rbx+r12*8]
0x180012165  mov     qword ptr [rsp+0A8h+var_88], rax; __int64
0x18001216a  call    WPP_SF_SSS
0x18001216f  jmp     loc_180011EC0
0x180012174  mov     rcx, cs:WPP_GLOBAL_Control
0x18001217b  cmp     rcx, r13
0x18001217e  jz      loc_180011EF7
0x180012184  cmp     byte ptr [rcx+0E1h], 1
0x18001218b  jb      loc_180011EF7
0x180012191  test    byte ptr [rcx+0E4h], 40h
0x180012198  jz      loc_180011EF7
0x18001219e  mov     eax, [rbx+6Ch]
0x1800121a1  mov     r9, rdi
0x1800121a4  mov     rcx, [rcx+0D8h]; LoggerHandle
0x1800121ab  mov     dword ptr [rsp+0A8h+var_58], 3F3h; char
0x1800121b3  mov     [rsp+0A8h+var_60], rdx; __int64
0x1800121b8  mov     dword ptr [rsp+0A8h+var_68], esi; char
0x1800121bc  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x1800121c0  mov     rax, [rbx+70h]
0x1800121c4  mov     [rsp+0A8h+var_78], rax; __int64
0x1800121c9  mov     eax, [rbx+68h]
0x1800121cc  mov     dword ptr [rsp+0A8h+var_80], eax; char
0x1800121d0  mov     qword ptr [rsp+0A8h+var_88], rbx; char
0x1800121d5  call    WPP_SF_qqdsddsd
0x1800121da  lea     rdx, aWdiagprocessac_4; "WDiagProcessAcmScanSMTransition"
0x1800121e1  jmp     loc_180011EF7
0x1800121e6  mov     rax, cs:WPP_GLOBAL_Control
0x1800121ed  cmp     rax, r13
0x1800121f0  jz      loc_180011F24
0x1800121f6  cmp     byte ptr [rax+0E1h], 1
0x1800121fd  jb      loc_180011F24
0x180012203  test    byte ptr [rax+0E4h], 40h
0x18001220a  jz      loc_180011F24
0x180012210  call    cs:__imp_GetCurrentThreadId
0x180012216  mov     dword ptr [rsp+0A8h+var_58], esi; char
0x18001221a  lea     rcx, aWdiagprocessac_4; "WDiagProcessAcmScanSMTransition"
0x180012221  mov     [rsp+0A8h+var_60], rcx; __int64
0x180012226  mov     r9, rdi
0x180012229  mov     rcx, cs:WPP_GLOBAL_Control
0x180012230  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x180012234  mov     eax, [rbx+78h]
0x180012237  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x18001223b  mov     rax, [rbx+80h]
0x180012242  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180012249  mov     [rsp+0A8h+var_78], rax; __int64
0x18001224e  mov     qword ptr [rsp+0A8h+var_88], rbx; char
0x180012253  call    WPP_SF_qqDsdDsd
0x180012258  lea     rdx, aWdiagprocessac_4; "WDiagProcessAcmScanSMTransition"
0x18001225f  jmp     loc_180011F24
```
