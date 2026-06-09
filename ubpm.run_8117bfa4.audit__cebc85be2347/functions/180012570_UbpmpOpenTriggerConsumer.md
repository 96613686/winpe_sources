# UbpmpOpenTriggerConsumer

- ea: `0x180012570`
- end: `0x18001294a`
- name: `UbpmpOpenTriggerConsumer`
- size: `986`
- prototype: `__int64 __fastcall(UUID *Uuid2, wchar_t *String2)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000f880`
- `0x180011480`
- `0x180011890`
- `0x180011a90`
- `0x1800136b0`

## callees

- `0x180012570`
- `0x180035184`
- `0x180037a10`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001267d`
- `msvcrt!_wcsicmp` at `0x180012837`
- `msvcrt!_wcsicmp` at `0x18001267d`
- `msvcrt!_wcsicmp` at `0x180012837`
- `ntdll!RtlReleaseSRWLockShared` at `0x180012713`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001275c`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800127c4`
- `ntdll!RtlReleaseSRWLockShared` at `0x180012809`
- `ntdll!RtlReleaseSRWLockShared` at `0x180012713`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001275c`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800127c4`
- `ntdll!RtlReleaseSRWLockShared` at `0x180012809`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800125ec`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001263e`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800126ef`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800126ff`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800125ec`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001263e`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800126ef`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800126ff`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800125b6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800125c7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180012605`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180012616`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180012796`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800127db`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800125b6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800125c7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180012605`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180012616`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180012796`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800127db`
- `RPCRT4!UuidEqual` at `0x1800126a4`
- `RPCRT4!UuidEqual` at `0x1800126d7`
- `RPCRT4!UuidEqual` at `0x1800126a4`
- `RPCRT4!UuidEqual` at `0x1800126d7`

## pseudocode

```c
__int64 __fastcall UbpmpOpenTriggerConsumer(UUID *Uuid2, wchar_t *String2, _QWORD *a3)
{
  unsigned int v3; // r15d
  DWORD v5; // esi
  _QWORD *Value; // rbx
  DWORD v9; // esi
  _QWORD *v10; // rbx
  _UNKNOWN **i; // rbx
  _UNKNOWN **v12; // rsi
  char v13; // bl
  __int64 *v14; // rax
  __int64 v15; // r8
  bool v16; // zf
  __int64 *v17; // rax
  __int64 v18; // r8
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  RPC_STATUS Status; // [rsp+80h] [rbp+18h] BYREF

  v3 = 1168;
  v5 = UbpmpLockTrackerId;
  Status = 0;
  *a3 = 0;
  if ( v5 != -1 )
  {
    Value = TlsGetValue(v5);
    if ( *(_QWORD *)TlsGetValue(v5) )
      __int2c();
    *Value |= 1uLL;
    ++Value[1];
  }
  RtlAcquireSRWLockShared(&g_ConsumerUpdateLock);
  v9 = UbpmpLockTrackerId;
  if ( UbpmpLockTrackerId != -1 )
  {
    v10 = TlsGetValue(UbpmpLockTrackerId);
    if ( (*(_QWORD *)TlsGetValue(v9) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      __int2c();
    *v10 |= 2uLL;
    ++v10[2];
  }
  RtlAcquireSRWLockShared(&g_ConsumerListLock);
  for ( i = (_UNKNOWN **)g_leConsumerListHead; ; i = (_UNKNOWN **)*i )
  {
    if ( i == &g_leConsumerListHead )
      goto LABEL_25;
    v12 = i - 1;
    if ( String2 )
    {
      if ( !_wcsicmp(*((const wchar_t **)v12[3] + 1), String2) )
        break;
    }
    if ( Uuid2 && UuidEqual(*(UUID **)v12[3], Uuid2, &Status) )
    {
      v3 = 0;
      if ( String2 && _wcsicmp(*((const wchar_t **)v12[3] + 1), String2) )
      {
        v3 = 87;
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v21 = 13;
LABEL_41:
          WPP_SF_S(v20[2], v21, WPP_d9ec29665f893a54f0af621b09fac3ba_Traceguids, String2);
          goto LABEL_25;
        }
        goto LABEL_25;
      }
LABEL_18:
      RtlAcquireSRWLockShared(v12 + 6);
      RtlAcquireSRWLockShared(v12 + 9);
      v13 = *((_BYTE *)v12 + 92);
      RtlReleaseSRWLockShared(v12 + 9);
      if ( (v13 & 1) != 0 || (*((_BYTE *)v12 + 41) & 1) == 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            WPP_d9ec29665f893a54f0af621b09fac3ba_Traceguids,
            *((_QWORD *)v12[3] + 1));
        v3 = 1235;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_Siq(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            (unsigned int)WPP_d9ec29665f893a54f0af621b09fac3ba_Traceguids,
            *((_QWORD *)v12[3] + 1),
            (char)v12[8],
            (char)v12);
        _InterlockedIncrement64((volatile signed __int64 *)v12 + 8);
        *a3 = v12;
      }
      RtlReleaseSRWLockShared(v12 + 6);
      goto LABEL_25;
    }
  }
  v3 = 0;
  if ( !Uuid2 || UuidEqual(*(UUID **)v12[3], Uuid2, &Status) )
    goto LABEL_18;
  v3 = 87;
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v21 = 12;
    goto LABEL_41;
  }
LABEL_25:
  if ( UbpmpLockTrackerId != -1 )
  {
    v14 = (__int64 *)TlsGetValue(UbpmpLockTrackerId);
    v15 = *v14;
    if ( (*v14 & 2) == 0 )
      __int2c();
    v16 = v14[2]-- == 1;
    if ( v16 )
      *v14 = v15 & 0xFFFFFFFFFFFFFFFDuLL;
  }
  RtlReleaseSRWLockShared(&g_ConsumerListLock);
  if ( UbpmpLockTrackerId != -1 )
  {
    v17 = (__int64 *)TlsGetValue(UbpmpLockTrackerId);
    v18 = *v17;
    if ( (*v17 & 1) == 0 )
      __int2c();
    v16 = v17[1]-- == 1;
    if ( v16 )
      *v17 = v18 & 0xFFFFFFFFFFFFFFFEuLL;
  }
  RtlReleaseSRWLockShared(&g_ConsumerUpdateLock);
  return v3;
}

```

## disassembly

```asm
0x180012570  mov     r11, rsp
0x180012573  push    r15
0x180012575  sub     rsp, 60h
0x180012579  mov     [r11+8], rbx
0x18001257d  xor     eax, eax
0x18001257f  mov     [r11-10h], rbp
0x180012583  mov     r15d, 490h
0x180012589  mov     [r11-18h], rsi
0x18001258d  mov     rbp, rdx
0x180012590  mov     esi, cs:UbpmpLockTrackerId
0x180012596  mov     [r11-20h], rdi
0x18001259a  mov     rdi, rcx
0x18001259d  mov     [r11-28h], r12
0x1800125a1  mov     r12, r8
0x1800125a4  mov     [r11-30h], r13
0x1800125a8  mov     [r11+18h], eax
0x1800125ac  mov     [r8], rax
0x1800125af  cmp     esi, 0FFFFFFFFh
0x1800125b2  jz      short loc_1800125E5
0x1800125b4  mov     ecx, esi; dwTlsIndex
0x1800125b6  call    cs:__imp_TlsGetValue
0x1800125bd  nop     dword ptr [rax+rax+00h]
0x1800125c2  mov     ecx, esi; dwTlsIndex
0x1800125c4  mov     rbx, rax
0x1800125c7  call    cs:__imp_TlsGetValue
0x1800125ce  nop     dword ptr [rax+rax+00h]
0x1800125d3  cmp     qword ptr [rax], 0
0x1800125d7  jnz     loc_18001289D
0x1800125dd  or      qword ptr [rbx], 1
0x1800125e1  inc     qword ptr [rbx+8]
0x1800125e5  lea     rcx, ?g_ConsumerUpdateLock@@3U_CEM_LOCK@@A; _CEM_LOCK g_ConsumerUpdateLock
0x1800125ec  call    cs:__imp_RtlAcquireSRWLockShared
0x1800125f3  nop     dword ptr [rax+rax+00h]
0x1800125f8  mov     esi, cs:UbpmpLockTrackerId
0x1800125fe  cmp     esi, 0FFFFFFFFh
0x180012601  jz      short loc_180012637
0x180012603  mov     ecx, esi; dwTlsIndex
0x180012605  call    cs:__imp_TlsGetValue
0x18001260c  nop     dword ptr [rax+rax+00h]
0x180012611  mov     ecx, esi; dwTlsIndex
0x180012613  mov     rbx, rax
0x180012616  call    cs:__imp_TlsGetValue
0x18001261d  nop     dword ptr [rax+rax+00h]
0x180012622  test    qword ptr [rax], 0FFFFFFFFFFFFFFFEh
0x180012629  jnz     loc_1800128A4
0x18001262f  or      qword ptr [rbx], 2
0x180012633  inc     qword ptr [rbx+10h]
0x180012637  lea     rcx, ?g_ConsumerListLock@@3U_CEM_LOCK@@A; _CEM_LOCK g_ConsumerListLock
0x18001263e  call    cs:__imp_RtlAcquireSRWLockShared
0x180012645  nop     dword ptr [rax+rax+00h]
0x18001264a  mov     rbx, cs:g_leConsumerListHead
0x180012651  lea     r13, g_leConsumerListHead
0x180012658  mov     [rsp+68h+var_38], r14
0x18001265d  nop     dword ptr [rax]
0x180012660  cmp     rbx, r13
0x180012663  jz      loc_180012768
0x180012669  lea     rsi, [rbx-8]
0x18001266d  test    rbp, rbp
0x180012670  jz      short loc_18001268D
0x180012672  mov     rcx, [rsi+18h]
0x180012676  mov     rdx, rbp; String2
0x180012679  mov     rcx, [rcx+8]; String1
0x18001267d  call    cs:__imp__wcsicmp
0x180012684  nop     dword ptr [rax+rax+00h]
0x180012689  test    eax, eax
0x18001268b  jz      short loc_1800126BD
0x18001268d  test    rdi, rdi
0x180012690  jz      short loc_1800126B8
0x180012692  mov     rcx, [rsi+18h]
0x180012696  lea     r8, [rsp+68h+Status]; Status
0x18001269e  mov     rdx, rdi; Uuid2
0x1800126a1  mov     rcx, [rcx]; Uuid1
0x1800126a4  call    cs:__imp_UuidEqual
0x1800126ab  nop     dword ptr [rax+rax+00h]
0x1800126b0  test    eax, eax
0x1800126b2  jnz     loc_180012820
0x1800126b8  mov     rbx, [rbx]
0x1800126bb  jmp     short loc_180012660
0x1800126bd  xor     r15d, r15d
0x1800126c0  test    rdi, rdi
0x1800126c3  jz      short loc_1800126EB
0x1800126c5  mov     rcx, [rsi+18h]
0x1800126c9  lea     r8, [rsp+68h+Status]; Status
0x1800126d1  mov     rdx, rdi; Uuid2
0x1800126d4  mov     rcx, [rcx]; Uuid1
0x1800126d7  call    cs:__imp_UuidEqual
0x1800126de  nop     dword ptr [rax+rax+00h]
0x1800126e3  test    eax, eax
0x1800126e5  jz      loc_1800128AB
0x1800126eb  lea     rcx, [rsi+30h]
0x1800126ef  call    cs:__imp_RtlAcquireSRWLockShared
0x1800126f6  nop     dword ptr [rax+rax+00h]
0x1800126fb  lea     rcx, [rsi+48h]
0x1800126ff  call    cs:__imp_RtlAcquireSRWLockShared
0x180012706  nop     dword ptr [rax+rax+00h]
0x18001270b  movzx   ebx, byte ptr [rsi+5Ch]
0x18001270f  lea     rcx, [rsi+48h]
0x180012713  call    cs:__imp_RtlReleaseSRWLockShared
0x18001271a  nop     dword ptr [rax+rax+00h]
0x18001271f  test    bl, 1
0x180012722  jnz     loc_180012909
0x180012728  test    byte ptr [rsi+29h], 1
0x18001272c  jz      loc_180012909
0x180012732  mov     rcx, cs:WPP_GLOBAL_Control
0x180012739  lea     rax, WPP_GLOBAL_Control
0x180012740  cmp     rcx, rax
0x180012743  jz      short loc_18001274F
0x180012745  test    byte ptr [rcx+1Ch], 8
0x180012749  jnz     loc_1800128D9
0x18001274f  lock inc qword ptr [rsi+40h]
0x180012754  mov     [r12], rsi
0x180012758  lea     rcx, [rsi+30h]
0x18001275c  call    cs:__imp_RtlReleaseSRWLockShared
0x180012763  nop     dword ptr [rax+rax+00h]
0x180012768  mov     ecx, cs:UbpmpLockTrackerId; dwTlsIndex
0x18001276e  mov     r14, [rsp+68h+var_38]
0x180012773  mov     r13, [rsp+68h+var_30]
0x180012778  mov     r12, [rsp+68h+var_28]
0x18001277d  mov     rdi, [rsp+68h+var_20]
0x180012782  mov     rsi, [rsp+68h+var_18]
0x180012787  mov     rbp, [rsp+68h+var_10]
0x18001278c  mov     rbx, [rsp+68h+arg_0]
0x180012791  cmp     ecx, 0FFFFFFFFh
0x180012794  jz      short loc_1800127BD
0x180012796  call    cs:__imp_TlsGetValue
0x18001279d  nop     dword ptr [rax+rax+00h]
0x1800127a2  mov     r8, [rax]
0x1800127a5  test    r8b, 2
0x1800127a9  jz      loc_18001288F
0x1800127af  sub     qword ptr [rax+10h], 1
0x1800127b4  jnz     short loc_1800127BD
0x1800127b6  and     r8, 0FFFFFFFFFFFFFFFDh
0x1800127ba  mov     [rax], r8
0x1800127bd  lea     rcx, ?g_ConsumerListLock@@3U_CEM_LOCK@@A; _CEM_LOCK g_ConsumerListLock
0x1800127c4  call    cs:__imp_RtlReleaseSRWLockShared
0x1800127cb  nop     dword ptr [rax+rax+00h]
0x1800127d0  mov     ecx, cs:UbpmpLockTrackerId; dwTlsIndex
0x1800127d6  cmp     ecx, 0FFFFFFFFh
0x1800127d9  jz      short loc_180012802
0x1800127db  call    cs:__imp_TlsGetValue
0x1800127e2  nop     dword ptr [rax+rax+00h]
0x1800127e7  mov     r8, [rax]
0x1800127ea  test    r8b, 1
0x1800127ee  jz      loc_180012896
0x1800127f4  sub     qword ptr [rax+8], 1
0x1800127f9  jnz     short loc_180012802
0x1800127fb  and     r8, 0FFFFFFFFFFFFFFFEh
0x1800127ff  mov     [rax], r8
0x180012802  lea     rcx, ?g_ConsumerUpdateLock@@3U_CEM_LOCK@@A; _CEM_LOCK g_ConsumerUpdateLock
0x180012809  call    cs:__imp_RtlReleaseSRWLockShared
0x180012810  nop     dword ptr [rax+rax+00h]
0x180012815  mov     eax, r15d
0x180012818  add     rsp, 60h
0x18001281c  pop     r15
0x18001281e  retn
0x180012820  xor     r15d, r15d
0x180012823  test    rbp, rbp
0x180012826  jz      loc_1800126EB
0x18001282c  mov     rcx, [rsi+18h]
0x180012830  mov     rdx, rbp; String2
0x180012833  mov     rcx, [rcx+8]; String1
0x180012837  call    cs:__imp__wcsicmp
0x18001283e  nop     dword ptr [rax+rax+00h]
0x180012843  test    eax, eax
0x180012845  jz      loc_1800126EB
0x18001284b  mov     r15d, 57h ; 'W'
0x180012851  mov     rcx, cs:WPP_GLOBAL_Control
0x180012858  lea     rax, WPP_GLOBAL_Control
0x18001285f  cmp     rcx, rax
0x180012862  jz      loc_180012768
0x180012868  test    byte ptr [rcx+1Ch], 1
0x18001286c  jz      loc_180012768
0x180012872  mov     edx, 0Dh
0x180012877  mov     rcx, [rcx+10h]
0x18001287b  lea     r8, WPP_d9ec29665f893a54f0af621b09fac3ba_Traceguids
0x180012882  mov     r9, rbp
0x180012885  call    WPP_SF_S
0x18001288a  jmp     loc_180012768
0x18001288f  int     2Ch; Windows NT - assertion failure
0x180012891  jmp     loc_1800127AF
0x180012896  int     2Ch; Windows NT - assertion failure
0x180012898  jmp     loc_1800127F4
0x18001289d  int     2Ch; Windows NT - assertion failure
0x18001289f  jmp     loc_1800125DD
0x1800128a4  int     2Ch; Windows NT - assertion failure
0x1800128a6  jmp     loc_18001262F
0x1800128ab  mov     r15d, 57h ; 'W'
0x1800128b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800128b8  lea     rax, WPP_GLOBAL_Control
0x1800128bf  cmp     rcx, rax
0x1800128c2  jz      loc_180012768
0x1800128c8  test    byte ptr [rcx+1Ch], 1
0x1800128cc  jz      loc_180012768
0x1800128d2  mov     edx, 0Ch
0x1800128d7  jmp     short loc_180012877
0x1800128d9  mov     rax, [rsi+18h]
0x1800128dd  lea     r8, WPP_d9ec29665f893a54f0af621b09fac3ba_Traceguids
0x1800128e4  mov     rcx, [rcx+10h]
0x1800128e8  mov     edx, 0Eh
0x1800128ed  mov     [rsp+68h+var_40], rsi
0x1800128f2  mov     r9, [rax+8]
0x1800128f6  mov     rax, [rsi+40h]
0x1800128fa  mov     [rsp+68h+var_48], rax
0x1800128ff  call    WPP_SF_Siq
0x180012904  jmp     loc_18001274F
0x180012909  mov     rcx, cs:WPP_GLOBAL_Control
0x180012910  lea     rax, WPP_GLOBAL_Control
0x180012917  cmp     rcx, rax
0x18001291a  jz      short loc_18001293F
0x18001291c  test    byte ptr [rcx+1Ch], 4
0x180012920  jz      short loc_18001293F
0x180012922  mov     r9, [rsi+18h]
0x180012926  lea     r8, WPP_d9ec29665f893a54f0af621b09fac3ba_Traceguids
0x18001292d  mov     rcx, [rcx+10h]
0x180012931  mov     edx, 0Fh
0x180012936  mov     r9, [r9+8]
0x18001293a  call    WPP_SF_S
0x18001293f  mov     r15d, 4D3h
0x180012945  jmp     loc_180012758
```
