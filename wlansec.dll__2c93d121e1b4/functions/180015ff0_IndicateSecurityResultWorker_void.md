# IndicateSecurityResultWorker(void *)

- ea: `0x180015ff0`
- end: `0x1800163d3`
- name: `?IndicateSecurityResultWorker@@YAKPEAX@Z`
- size: `995`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000431c`
- `0x1800063b0`
- `0x18000892c`
- `0x180008998`
- `0x18000bde0`
- `0x180014d24`
- `0x180015ff0`
- `0x1800163e0`
- `0x180016470`
- `0x18002e310`
- `0x18003346c`
- `0x180033be0`
- `0x18003823c`
- `0x180038518`
- `0x180043a30`
- `0x18004456c`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180016084`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180016084`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800160b4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800160b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001628f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001628f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800162bc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800162bc`
- `OneX!OneXReasonCodeToString` at `0x1800162db`
- `OneX!OneXReasonCodeToString` at `0x1800162db`

## string_xrefs

- `0x180016152`: `IndicateSecurityResultWorker`
- `0x18001607d`: `wlansvc.dll`

## pseudocode

```c
__int64 __fastcall IndicateSecurityResultWorker(HMODULE Parameter)
{
  unsigned int v2; // edi
  __int64 v3; // r8
  DWORD LastError; // eax
  int v5; // edx
  int v6; // ecx
  DWORD v7; // esi
  PVOID *v8; // rdi
  unsigned int v9; // eax
  const struct _GUID *v10; // r9
  unsigned int v11; // edi
  HMODULE phModule[2]; // [rsp+70h] [rbp-90h] BYREF
  _WORD v14[256]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(v14, 0, sizeof(v14));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 62, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids);
  if ( Microsoft_Windows_Networking_CorrelationEnabled )
  {
    phModule[1] = *((HMODULE *)&Microsoft_Windows_Networking_ProviderId + 1);
    phModule[0] = Parameter;
    EventActivityIdControl(2u, (LPGUID)phModule);
  }
  v2 = *((_DWORD *)Parameter + 8);
  phModule[0] = 0;
  if ( v2 - 327680 <= 0xFFFF )
  {
    LastError = OneXReasonCodeToString(v2, 256, v14, 0);
  }
  else if ( GetModuleHandleExW(0, L"wlansvc.dll", phModule) )
  {
    LastError = AcmReasonCodeToString(phModule[0], v2, v3, v14);
  }
  else
  {
    LastError = GetLastError();
  }
  v6 = (int)phModule[0];
  v7 = LastError;
  if ( phModule[0] )
    FreeLibrary(phModule[0]);
  if ( !v7 )
    goto LABEL_10;
  v14[0] = 0;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_12;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      63,
      &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids,
      *((unsigned int *)Parameter + 8),
      v7);
LABEL_10:
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v8 + 68) & 2) != 0 )
    {
      WPP_SF_LDDDDDDLSD(
        (unsigned int)v8[7],
        *((unsigned __int8 *)Parameter + 28),
        *((unsigned __int8 *)Parameter + 27),
        *(_DWORD *)Parameter,
        *((_BYTE *)Parameter + 24),
        *((_BYTE *)Parameter + 25),
        *((_BYTE *)Parameter + 26),
        *((_BYTE *)Parameter + 27),
        *((_BYTE *)Parameter + 28),
        *((_BYTE *)Parameter + 29),
        *((_DWORD *)Parameter + 8),
        (__int64)v14,
        *((_DWORD *)Parameter + 9));
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 68) & 2) != 0 )
      WPP_SF_Lq(
        v8[7],
        65,
        &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids,
        *(_DWORD *)Parameter,
        *((_QWORD *)Parameter + 2));
  }
LABEL_12:
  if ( (byte_1800AED45 & 1) != 0 )
    McTemplateU0qb6qq_EventWriteTransfer(
      v6,
      v5,
      *(_DWORD *)Parameter,
      (_DWORD)Parameter + 24,
      *((_DWORD *)Parameter + 8),
      *((_DWORD *)Parameter + 9));
  if ( *((_DWORD *)Parameter + 10) )
    UpdateIntfProfileKey(*((void **)Parameter + 1), *((void **)Parameter + 6), *((void **)Parameter + 7));
  v9 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, char *, _QWORD, _DWORD))Parameter + 9))(
         *((_QWORD *)Parameter + 1),
         *((_QWORD *)Parameter + 2),
         (char *)Parameter + 24,
         *((unsigned int *)Parameter + 8),
         *((_DWORD *)Parameter + 9));
  v11 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 66, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids, v9);
  }
  else
  {
    PostSecurityActions((struct MSMSEC_INDICATE_SECURITY_RESULT_CONTEXT *)Parameter);
  }
  if ( Microsoft_Windows_Networking_CorrelationEnabled )
  {
    phModule[1] = *((HMODULE *)&Microsoft_Windows_Networking_ProviderId + 1);
    phModule[0] = Parameter;
    EtwEx_tidActivityInfo(
      Microsoft_Windows_Networking_CorrelationHandle,
      &ActivityStop,
      (const struct _GUID *)phModule,
      v10,
      0x12u);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_13d7b2876eef3b3479d595a943243812_Traceguids, Parameter);
  FreeWLMemory(Parameter);
  DecThreadCountEx("IndicateSecurityResultWorker", 657);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 67, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x180015ff0  push    rbp
0x180015ff2  push    rbx
0x180015ff3  push    rsi
0x180015ff4  push    rdi
0x180015ff5  push    r12
0x180015ff7  push    r14
0x180015ff9  lea     rbp, [rsp-198h]
0x180016001  sub     rsp, 298h
0x180016008  mov     rax, cs:__security_cookie
0x18001600f  xor     rax, rsp
0x180016012  mov     [rbp+1C0h+var_40], rax
0x180016019  mov     rbx, rcx
0x18001601c  xor     edx, edx; Val
0x18001601e  lea     rcx, [rbp+1C0h+var_240]; void *
0x180016022  mov     r8d, 200h; Size
0x180016028  call    memset_0
0x18001602d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016034  lea     r14, WPP_GLOBAL_Control
0x18001603b  lea     r12, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x180016042  cmp     rcx, r14
0x180016045  jnz     loc_180016205
0x18001604b  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x180016051  test    eax, eax
0x180016053  jnz     loc_1800162A0
0x180016059  mov     edi, [rbx+20h]
0x18001605c  mov     [rsp+2C0h+phModule], 0
0x180016065  lea     eax, [rdi-50000h]
0x18001606b  cmp     eax, 0FFFFh
0x180016070  jbe     loc_1800162CD
0x180016076  lea     r8, [rsp+2C0h+phModule]; phModule
0x18001607b  xor     ecx, ecx; dwFlags
0x18001607d  lea     rdx, ModuleName; "wlansvc.dll"
0x180016084  call    cs:__imp_GetModuleHandleExW
0x18001608b  nop     dword ptr [rax+rax+00h]
0x180016090  test    eax, eax
0x180016092  jz      loc_18001628F
0x180016098  mov     rcx, [rsp+2C0h+phModule]
0x18001609d  lea     r9, [rbp+1C0h+var_240]
0x1800160a1  mov     edx, edi
0x1800160a3  call    AcmReasonCodeToString
0x1800160a8  mov     rcx, [rsp+2C0h+phModule]; hLibModule
0x1800160ad  mov     esi, eax
0x1800160af  test    rcx, rcx
0x1800160b2  jz      short loc_1800160C0
0x1800160b4  call    cs:__imp_FreeLibrary
0x1800160bb  nop     dword ptr [rax+rax+00h]
0x1800160c0  test    esi, esi
0x1800160c2  jnz     loc_1800162EC
0x1800160c8  mov     rdi, cs:WPP_GLOBAL_Control
0x1800160cf  cmp     rdi, r14
0x1800160d2  jnz     loc_1800161CA
0x1800160d8  test    cs:byte_1800AED45, 1
0x1800160df  jnz     loc_18001618C
0x1800160e5  cmp     dword ptr [rbx+28h], 0
0x1800160e9  jnz     loc_180016328
0x1800160ef  mov     ecx, [rbx+24h]
0x1800160f2  lea     r8, [rbx+18h]
0x1800160f6  mov     r9d, [rbx+20h]
0x1800160fa  mov     rdx, [rbx+10h]
0x1800160fe  mov     rax, [rbx+48h]
0x180016102  mov     [rsp+2C0h+var_2A0], ecx
0x180016106  mov     rcx, [rbx+8]
0x18001610a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001610f  mov     edi, eax
0x180016111  test    eax, eax
0x180016113  jnz     loc_18001633E
0x180016119  mov     rcx, rbx; struct MSMSEC_INDICATE_SECURITY_RESULT_CONTEXT *
0x18001611c  call    ?PostSecurityActions@@YAKPEAUMSMSEC_INDICATE_SECURITY_RESULT_CONTEXT@@@Z; PostSecurityActions(MSMSEC_INDICATE_SECURITY_RESULT_CONTEXT *)
0x180016121  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x180016127  test    eax, eax
0x180016129  jnz     loc_180016371
0x18001612f  mov     rcx, cs:WPP_GLOBAL_Control
0x180016136  cmp     rcx, r14
0x180016139  jz      short loc_180016145
0x18001613b  test    byte ptr [rcx+1Ch], 10h
0x18001613f  jnz     loc_1800163B6
0x180016145  mov     rcx, rbx
0x180016148  call    FreeWLMemory
0x18001614d  mov     edx, 291h; int
0x180016152  lea     rcx, aIndicatesecuri; "IndicateSecurityResultWorker"
0x180016159  call    ?DecThreadCountEx@@YAXPEBDH@Z; DecThreadCountEx(char const *,int)
0x18001615e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016165  cmp     rcx, r14
0x180016168  jnz     short loc_1800161AB
0x18001616a  mov     eax, edi
0x18001616c  mov     rcx, [rbp+1C0h+var_40]
0x180016173  xor     rcx, rsp; StackCookie
0x180016176  call    __security_check_cookie
0x18001617b  add     rsp, 298h
0x180016182  pop     r14
0x180016184  pop     r12
0x180016186  pop     rdi
0x180016187  pop     rsi
0x180016188  pop     rbx
0x180016189  pop     rbp
0x18001618a  retn
0x18001618c  mov     eax, [rbx+24h]
0x18001618f  lea     r9, [rbx+18h]
0x180016193  mov     r8d, [rbx]
0x180016196  mov     [rsp+2C0h+var_298], eax
0x18001619a  mov     eax, [rbx+20h]
0x18001619d  mov     [rsp+2C0h+var_2A0], eax
0x1800161a1  call    McTemplateU0qb6qq_EventWriteTransfer
0x1800161a6  jmp     loc_1800160E5
0x1800161ab  test    dword ptr [rcx+44h], 100h
0x1800161b2  jz      short loc_18001616A
0x1800161b4  mov     rcx, [rcx+38h]
0x1800161b8  mov     edx, 43h ; 'C'
0x1800161bd  mov     r9d, edi
0x1800161c0  mov     r8, r12
0x1800161c3  call    WPP_SF_d
0x1800161c8  jmp     short loc_18001616A
0x1800161ca  test    byte ptr [rdi+44h], 2
0x1800161ce  jnz     short loc_180016228
0x1800161d0  cmp     rdi, r14
0x1800161d3  jz      loc_1800160D8
0x1800161d9  test    byte ptr [rdi+44h], 2
0x1800161dd  jz      loc_1800160D8
0x1800161e3  mov     rax, [rbx+10h]
0x1800161e7  mov     edx, 41h ; 'A'
0x1800161ec  mov     r9d, [rbx]
0x1800161ef  mov     r8, r12
0x1800161f2  mov     rcx, [rdi+38h]
0x1800161f6  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x1800161fb  call    WPP_SF_Lq
0x180016200  jmp     loc_1800160D8
0x180016205  test    dword ptr [rcx+44h], 100h
0x18001620c  jz      loc_18001604B
0x180016212  mov     rcx, [rcx+38h]
0x180016216  mov     edx, 3Eh ; '>'
0x18001621b  mov     r8, r12
0x18001621e  call    WPP_SF_
0x180016223  jmp     loc_18001604B
0x180016228  mov     eax, [rbx+24h]
0x18001622b  movzx   ecx, byte ptr [rbx+1Dh]
0x18001622f  movzx   r9d, byte ptr [rbx+1Ah]
0x180016234  movzx   edx, byte ptr [rbx+1Ch]
0x180016238  movzx   r8d, byte ptr [rbx+1Bh]
0x18001623d  movzx   r10d, byte ptr [rbx+19h]
0x180016242  movzx   r11d, byte ptr [rbx+18h]
0x180016247  mov     [rsp+2C0h+var_260], eax
0x18001624b  lea     rax, [rbp+1C0h+var_240]
0x18001624f  mov     [rsp+2C0h+var_268], rax
0x180016254  mov     eax, [rbx+20h]
0x180016257  mov     [rsp+2C0h+var_270], eax
0x18001625b  mov     [rsp+2C0h+var_278], ecx
0x18001625f  mov     rcx, [rdi+38h]
0x180016263  mov     [rsp+2C0h+var_280], edx
0x180016267  mov     [rsp+2C0h+var_288], r8d
0x18001626c  mov     [rsp+2C0h+var_290], r9d
0x180016271  mov     r9d, [rbx]
0x180016274  mov     [rsp+2C0h+var_298], r10d
0x180016279  mov     [rsp+2C0h+var_2A0], r11d
0x18001627e  call    WPP_SF_LDDDDDDLSD
0x180016283  mov     rdi, cs:WPP_GLOBAL_Control
0x18001628a  jmp     loc_1800161D0
0x18001628f  call    cs:__imp_GetLastError
0x180016296  nop     dword ptr [rax+rax+00h]
0x18001629b  jmp     loc_1800160A8
0x1800162a0  movups  xmm0, cs:Microsoft_Windows_Networking_ProviderId
0x1800162a7  lea     rdx, [rsp+2C0h+phModule]; ActivityId
0x1800162ac  mov     ecx, 2; ControlCode
0x1800162b1  movdqu  xmmword ptr [rsp+2C0h+phModule], xmm0
0x1800162b7  mov     [rsp+2C0h+phModule], rbx
0x1800162bc  call    cs:__imp_EventActivityIdControl
0x1800162c3  nop     dword ptr [rax+rax+00h]
0x1800162c8  jmp     loc_180016059
0x1800162cd  xor     r9d, r9d
0x1800162d0  lea     r8, [rbp+1C0h+var_240]
0x1800162d4  mov     edx, 100h
0x1800162d9  mov     ecx, edi
0x1800162db  call    cs:__imp_OneXReasonCodeToString
0x1800162e2  nop     dword ptr [rax+rax+00h]
0x1800162e7  jmp     loc_1800160A8
0x1800162ec  xor     eax, eax
0x1800162ee  mov     [rbp+1C0h+var_240], ax
0x1800162f2  mov     rdi, cs:WPP_GLOBAL_Control
0x1800162f9  cmp     rdi, r14
0x1800162fc  jz      loc_1800160D8
0x180016302  test    byte ptr [rdi+44h], 1
0x180016306  jz      loc_1800160CF
0x18001630c  mov     r9d, [rbx+20h]
0x180016310  lea     edx, [rax+3Fh]
0x180016313  mov     rcx, [rdi+38h]
0x180016317  mov     r8, r12
0x18001631a  mov     [rsp+2C0h+var_2A0], esi
0x18001631e  call    WPP_SF_dd
0x180016323  jmp     loc_1800160C8
0x180016328  mov     r8, [rbx+38h]; void *
0x18001632c  mov     rdx, [rbx+30h]; void *
0x180016330  mov     rcx, [rbx+8]; void *
0x180016334  call    ?UpdateIntfProfileKey@@YAKPEAX00@Z; UpdateIntfProfileKey(void *,void *,void *)
0x180016339  jmp     loc_1800160EF
0x18001633e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016345  cmp     rcx, r14
0x180016348  jz      loc_180016121
0x18001634e  test    byte ptr [rcx+44h], 1
0x180016352  jz      loc_180016121
0x180016358  mov     rcx, [rcx+38h]
0x18001635c  mov     edx, 42h ; 'B'
0x180016361  mov     r9d, edi
0x180016364  mov     r8, r12
0x180016367  call    WPP_SF_d
0x18001636c  jmp     loc_180016121
0x180016371  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x180016377  test    eax, eax
0x180016379  jz      loc_18001612F
0x18001637f  movups  xmm0, cs:Microsoft_Windows_Networking_ProviderId
0x180016386  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x18001638d  lea     r8, [rsp+2C0h+phModule]; struct _GUID *
0x180016392  lea     rdx, ActivityStop; EventDescriptor
0x180016399  mov     [rsp+2C0h+var_2A0], 12h; unsigned int
0x1800163a1  movdqu  xmmword ptr [rsp+2C0h+phModule], xmm0
0x1800163a7  mov     [rsp+2C0h+phModule], rbx
0x1800163ac  call    ?EtwEx_tidActivityInfo@@YAK_KPEBU_EVENT_DESCRIPTOR@@PEBU_GUID@@2K@Z; EtwEx_tidActivityInfo(unsigned __int64,_EVENT_DESCRIPTOR const *,_GUID const *,_GUID const *,ulong)
0x1800163b1  jmp     loc_18001612F
0x1800163b6  mov     rcx, [rcx+10h]
0x1800163ba  lea     r8, WPP_13d7b2876eef3b3479d595a943243812_Traceguids
0x1800163c1  mov     edx, 0Ch
0x1800163c6  mov     r9, rbx
0x1800163c9  call    WPP_SF_q
0x1800163ce  jmp     loc_180016145
```
