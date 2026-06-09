# CWcnConnectionEngine::Init(_GUID const *,_DOT11_SSID const *,ulong,IWcnConnectionEngineCallback *)

- ea: `0x1800202d0`
- end: `0x1800205e5`
- name: `?Init@CWcnConnectionEngine@@QEAAJPEBU_GUID@@PEBU_DOT11_SSID@@KPEAVIWcnConnectionEngineCallback@@@Z`
- size: `789`
- prototype: `__int64 __usercall@<rax>(CWcnConnectionEngine *__hidden this@<rcx>, const struct _GUID *@<rdx>, const struct _DOT11_SSID *@<r8>, unsigned int@<r9d>, struct IWcnConnectionEngineCallback *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18001f968`

## callees

- `0x180001820`
- `0x180002981`
- `0x18000d630`
- `0x18000e1dc`
- `0x1800202d0`
- `0x180021664`
- `0x18002de1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002043c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020446`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020450`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800204ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800204b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800204c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002053a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020544`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002043c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020446`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020450`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800204ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800204b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800204c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002053a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020544`
- `KERNEL32!CreateEventW` at `0x18002042d`
- `KERNEL32!CreateEventW` at `0x18002049d`
- `KERNEL32!CreateEventW` at `0x18002042d`
- `KERNEL32!CreateEventW` at `0x18002049d`
- `KERNEL32!CreateThread` at `0x180020521`
- `KERNEL32!CreateThread` at `0x180020521`

## string_xrefs

- `0x180020352`: `pSsid`

## pseudocode

```c
__int64 __fastcall CWcnConnectionEngine::Init(
        CWcnConnectionEngine *this,
        const struct _GUID *a2,
        const struct _DOT11_SSID *a3,
        __int64 a4,
        struct IWcnConnectionEngineCallback *a5)
{
  _BYTE *v8; // r10
  const char *Indent; // rax
  __int64 v10; // r10
  __int64 v11; // rdx
  const char *v12; // r9
  _QWORD *v14; // rsi
  size_t uSSIDLength; // r8
  unsigned int v16; // eax
  int v17; // edx
  int v18; // r8d
  HANDLE EventW; // rax
  unsigned int v20; // ebx
  unsigned int v21; // ebx
  _BYTE *v22; // r10
  unsigned int v23; // eax
  __int64 v24; // r10
  int v25; // edx
  HANDLE v26; // rax
  unsigned int v27; // ebx
  HANDLE Thread; // rax
  unsigned int LastError; // ebx
  unsigned int v30; // eax
  __int64 v31; // r10
  _OWORD v32[2]; // [rsp+40h] [rbp-58h] BYREF
  char v33; // [rsp+60h] [rbp-38h]

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v10 + 16), 10, WPP_2ea1fd34665a3647954ba5ee5f2f60a4_Traceguids, Indent);
    v8 = WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    if ( v8 == (_BYTE *)&WPP_GLOBAL_Control || v8[25] < 2u )
      return 2147500035LL;
    v11 = 11;
    v12 = "pSsid";
LABEL_12:
    WPP_SF_s(*((_QWORD *)v8 + 2), v11, WPP_2ea1fd34665a3647954ba5ee5f2f60a4_Traceguids, v12);
    return 2147500035LL;
  }
  if ( !a5 )
  {
    if ( v8 == (_BYTE *)&WPP_GLOBAL_Control || v8[25] < 2u )
      return 2147500035LL;
    v11 = 12;
    v12 = "pCallback";
    goto LABEL_12;
  }
  *((_DWORD *)this + 10) = 1;
  *(struct _GUID *)((char *)this + 44) = *a2;
  *(_OWORD *)((char *)this + 60) = *(_OWORD *)&a3->uSSIDLength;
  *(_OWORD *)((char *)this + 76) = *(_OWORD *)&a3->ucSSID[12];
  *((_DWORD *)this + 23) = *(_DWORD *)&a3->ucSSID[28];
  *((_QWORD *)this + 20) = a5;
  v14 = WPP_GLOBAL_Control;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0 )
  {
    uSSIDLength = a3->uSSIDLength;
    memset(v32, 0, sizeof(v32));
    v33 = 0;
    memcpy_0(v32, a3->ucSSID, uSSIDLength);
    if ( v14 != &WPP_GLOBAL_Control && *((_BYTE *)v14 + 25) >= 5u )
    {
      v16 = (unsigned int)GetIndent(0);
      WPP_SF_s_guid_sD(v14[2], v17, v18, v16, (__int64)a2, (__int64)v32);
    }
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 4) = EventW;
  if ( EventW )
  {
    v26 = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 3) = v26;
    if ( v26 )
    {
      v21 = 0;
      *((_DWORD *)this + 42) = 2;
      Thread = CreateThread(0, 0, CWcnConnectionEngine::WorkerThreadThunk, this, 0, 0);
      *((_QWORD *)this + 2) = Thread;
      if ( Thread )
      {
LABEL_40:
        v22 = WPP_GLOBAL_Control;
        goto LABEL_41;
      }
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0x80070000;
      else
        LastError = GetLastError();
      v21 = LastError | 0x80000000;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v21;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_41;
      v23 = (unsigned int)GetIndent(0);
      v25 = 16;
    }
    else
    {
      if ( (int)GetLastError() > 0 )
        v27 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v27 = GetLastError();
      v21 = v27 | 0x80000000;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v21;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_41;
      v23 = (unsigned int)GetIndent(0);
      v25 = 15;
    }
LABEL_39:
    WPP_SF_sd(*(_QWORD *)(v24 + 16), v25, (unsigned int)WPP_2ea1fd34665a3647954ba5ee5f2f60a4_Traceguids, v23, v21);
    goto LABEL_40;
  }
  if ( (int)GetLastError() > 0 )
    v20 = (unsigned __int16)GetLastError() | 0x80070000;
  else
    v20 = GetLastError();
  v21 = v20 | 0x80000000;
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v21;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v23 = (unsigned int)GetIndent(0);
    v25 = 14;
    goto LABEL_39;
  }
LABEL_41:
  if ( v22 != (_BYTE *)&WPP_GLOBAL_Control && ((v21 & 0x80000000) != 0 || v22[25] >= 6u) )
  {
    v30 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v31 + 16), 17, (unsigned int)WPP_2ea1fd34665a3647954ba5ee5f2f60a4_Traceguids, v30, v21);
  }
  return v21;
}

```

## disassembly

```asm
0x1800202d0  mov     [rsp+arg_18], rbx
0x1800202d5  push    rbp
0x1800202d6  push    rsi
0x1800202d7  push    rdi
0x1800202d8  push    r14
0x1800202da  push    r15
0x1800202dc  sub     rsp, 70h
0x1800202e0  mov     rax, cs:__security_cookie
0x1800202e7  xor     rax, rsp
0x1800202ea  mov     [rsp+98h+var_30], rax
0x1800202ef  mov     rbx, r8
0x1800202f2  mov     rbp, rdx
0x1800202f5  mov     rdi, rcx
0x1800202f8  mov     r10, cs:WPP_GLOBAL_Control
0x1800202ff  lea     r14, WPP_GLOBAL_Control
0x180020306  lea     r15, WPP_2ea1fd34665a3647954ba5ee5f2f60a4_Traceguids
0x18002030d  cmp     r10, r14
0x180020310  jz      short loc_18002033E
0x180020312  cmp     byte ptr [r10+19h], 6
0x180020317  jb      short loc_18002033E
0x180020319  mov     ecx, 1; int
0x18002031e  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180020323  mov     rcx, [r10+10h]
0x180020327  mov     edx, 0Ah
0x18002032c  mov     r9, rax
0x18002032f  mov     r8, r15
0x180020332  call    WPP_SF_s
0x180020337  mov     r10, cs:WPP_GLOBAL_Control
0x18002033e  test    rbx, rbx
0x180020341  jnz     short loc_18002035B
0x180020343  cmp     r10, r14
0x180020346  jz      short loc_18002038A
0x180020348  cmp     byte ptr [r10+19h], 2
0x18002034d  jb      short loc_18002038A
0x18002034f  lea     edx, [rbx+0Bh]
0x180020352  lea     r9, aPssid; "pSsid"
0x180020359  jmp     short loc_18002037E
0x18002035b  mov     rcx, [rsp+98h+arg_20]
0x180020363  test    rcx, rcx
0x180020366  jnz     short loc_180020394
0x180020368  cmp     r10, r14
0x18002036b  jz      short loc_18002038A
0x18002036d  cmp     byte ptr [r10+19h], 2
0x180020372  jb      short loc_18002038A
0x180020374  lea     edx, [rcx+0Ch]
0x180020377  lea     r9, aPcallback; "pCallback"
0x18002037e  mov     rcx, [r10+10h]
0x180020382  mov     r8, r15
0x180020385  call    WPP_SF_s
0x18002038a  mov     eax, 80004003h
0x18002038f  jmp     loc_1800205C4
0x180020394  mov     dword ptr [rdi+28h], 1
0x18002039b  movups  xmm0, xmmword ptr [rbp+0]
0x18002039f  movdqu  xmmword ptr [rdi+2Ch], xmm0
0x1800203a4  movups  xmm0, xmmword ptr [rbx]
0x1800203a7  movups  xmmword ptr [rdi+3Ch], xmm0
0x1800203ab  movups  xmm1, xmmword ptr [rbx+10h]
0x1800203af  movups  xmmword ptr [rdi+4Ch], xmm1
0x1800203b3  mov     eax, [rbx+20h]
0x1800203b6  mov     [rdi+5Ch], eax
0x1800203b9  mov     [rdi+0A0h], rcx
0x1800203c0  mov     rsi, cs:WPP_GLOBAL_Control
0x1800203c7  test    dword ptr [rsi+1Ch], 20000h
0x1800203ce  jz      short loc_180020421
0x1800203d0  mov     r8d, [rbx]; Size
0x1800203d3  lea     rdx, [rbx+4]; Src
0x1800203d7  xorps   xmm0, xmm0
0x1800203da  lea     rcx, [rsp+98h+var_58]; void *
0x1800203df  xor     eax, eax
0x1800203e1  movups  [rsp+98h+var_58], xmm0
0x1800203e6  mov     [rsp+98h+var_38], al
0x1800203ea  movups  [rsp+98h+var_48], xmm0
0x1800203ef  call    memcpy_0
0x1800203f4  cmp     rsi, r14
0x1800203f7  jz      short loc_180020421
0x1800203f9  cmp     byte ptr [rsi+19h], 5
0x1800203fd  jb      short loc_180020421
0x1800203ff  xor     ecx, ecx; int
0x180020401  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180020406  lea     rcx, [rsp+98h+var_58]
0x18002040b  mov     r9, rax
0x18002040e  mov     [rsp+98h+lpThreadId], rcx
0x180020413  mov     rcx, [rsi+10h]
0x180020417  mov     qword ptr [rsp+98h+dwCreationFlags], rbp
0x18002041c  call    WPP_SF_s_guid_sD
0x180020421  xor     r9d, r9d; lpName
0x180020424  xor     r8d, r8d; bInitialState
0x180020427  xor     ecx, ecx; lpEventAttributes
0x180020429  lea     edx, [r9+1]; bManualReset
0x18002042d  call    cs:__imp_CreateEventW
0x180020433  mov     [rdi+20h], rax
0x180020437  test    rax, rax
0x18002043a  jnz     short loc_180020491
0x18002043c  call    cs:__imp_GetLastError
0x180020442  test    eax, eax
0x180020444  jg      short loc_180020450
0x180020446  call    cs:__imp_GetLastError
0x18002044c  mov     ebx, eax
0x18002044e  jmp     short loc_18002045F
0x180020450  call    cs:__imp_GetLastError
0x180020456  movzx   ebx, ax
0x180020459  or      ebx, 80070000h
0x18002045f  or      ebx, 80000000h
0x180020465  mov     r10, cs:WPP_GLOBAL_Control
0x18002046c  cmp     r10, r14
0x18002046f  jz      loc_1800205C2
0x180020475  cmp     byte ptr [r10+19h], 2
0x18002047a  jb      loc_180020592
0x180020480  xor     ecx, ecx; int
0x180020482  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180020487  mov     edx, 0Eh
0x18002048c  jmp     loc_180020578
0x180020491  xor     r9d, r9d; lpName
0x180020494  xor     r8d, r8d; bInitialState
0x180020497  xor     ecx, ecx; lpEventAttributes
0x180020499  lea     edx, [r9+1]; bManualReset
0x18002049d  call    cs:__imp_CreateEventW
0x1800204a3  mov     [rdi+18h], rax
0x1800204a7  test    rax, rax
0x1800204aa  jnz     short loc_1800204FE
0x1800204ac  call    cs:__imp_GetLastError
0x1800204b2  test    eax, eax
0x1800204b4  jg      short loc_1800204C0
0x1800204b6  call    cs:__imp_GetLastError
0x1800204bc  mov     ebx, eax
0x1800204be  jmp     short loc_1800204CF
0x1800204c0  call    cs:__imp_GetLastError
0x1800204c6  movzx   ebx, ax
0x1800204c9  or      ebx, 80070000h
0x1800204cf  or      ebx, 80000000h
0x1800204d5  mov     r10, cs:WPP_GLOBAL_Control
0x1800204dc  cmp     r10, r14
0x1800204df  jz      loc_1800205C2
0x1800204e5  cmp     byte ptr [r10+19h], 2
0x1800204ea  jb      loc_180020592
0x1800204f0  xor     ecx, ecx; int
0x1800204f2  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800204f7  mov     edx, 0Fh
0x1800204fc  jmp     short loc_180020578
0x1800204fe  xor     ebx, ebx
0x180020500  mov     dword ptr [rdi+0A8h], 2
0x18002050a  mov     [rsp+98h+lpThreadId], rbx; lpThreadId
0x18002050f  lea     r8, ?WorkerThreadThunk@CWcnConnectionEngine@@CAKPEAX@Z; lpStartAddress
0x180020516  mov     r9, rdi; lpParameter
0x180020519  mov     [rsp+98h+dwCreationFlags], ebx; dwCreationFlags
0x18002051d  xor     edx, edx; dwStackSize
0x18002051f  xor     ecx, ecx; lpThreadAttributes
0x180020521  call    cs:__imp_CreateThread
0x180020527  mov     [rdi+10h], rax
0x18002052b  test    rax, rax
0x18002052e  jnz     short loc_18002058B
0x180020530  call    cs:__imp_GetLastError
0x180020536  test    eax, eax
0x180020538  jg      short loc_180020544
0x18002053a  call    cs:__imp_GetLastError
0x180020540  mov     ebx, eax
0x180020542  jmp     short loc_180020553
0x180020544  call    cs:__imp_GetLastError
0x18002054a  movzx   ebx, ax
0x18002054d  or      ebx, 80070000h
0x180020553  or      ebx, 80000000h
0x180020559  mov     r10, cs:WPP_GLOBAL_Control
0x180020560  cmp     r10, r14
0x180020563  jz      short loc_1800205C2
0x180020565  cmp     byte ptr [r10+19h], 2
0x18002056a  jb      short loc_180020592
0x18002056c  xor     ecx, ecx; int
0x18002056e  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180020573  mov     edx, 10h
0x180020578  mov     rcx, [r10+10h]
0x18002057c  mov     r9, rax
0x18002057f  mov     r8, r15
0x180020582  mov     [rsp+98h+dwCreationFlags], ebx
0x180020586  call    WPP_SF_sd
0x18002058b  mov     r10, cs:WPP_GLOBAL_Control
0x180020592  cmp     r10, r14
0x180020595  jz      short loc_1800205C2
0x180020597  test    ebx, ebx
0x180020599  js      short loc_1800205A2
0x18002059b  cmp     byte ptr [r10+19h], 6
0x1800205a0  jb      short loc_1800205C2
0x1800205a2  or      ecx, 0FFFFFFFFh; int
0x1800205a5  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800205aa  mov     rcx, [r10+10h]
0x1800205ae  mov     edx, 11h
0x1800205b3  mov     r9, rax
0x1800205b6  mov     [rsp+98h+dwCreationFlags], ebx
0x1800205ba  mov     r8, r15
0x1800205bd  call    WPP_SF_sd
0x1800205c2  mov     eax, ebx
0x1800205c4  mov     rcx, [rsp+98h+var_30]
0x1800205c9  xor     rcx, rsp; StackCookie
0x1800205cc  call    __security_check_cookie
0x1800205d1  mov     rbx, [rsp+98h+arg_18]
0x1800205d9  add     rsp, 70h
0x1800205dd  pop     r15
0x1800205df  pop     r14
0x1800205e1  pop     rdi
0x1800205e2  pop     rsi
0x1800205e3  pop     rbp
0x1800205e4  retn
```
