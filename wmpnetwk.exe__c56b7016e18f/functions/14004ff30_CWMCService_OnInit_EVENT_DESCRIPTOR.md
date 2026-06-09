# CWMCService::OnInit(_EVENT_DESCRIPTOR &)

- ea: `0x14004ff30`
- end: `0x140050189`
- name: `?OnInit@CWMCService@@UEAAKAEAU_EVENT_DESCRIPTOR@@@Z`
- size: `601`
- prototype: `unsigned int __fastcall(CWMCService *__hidden this, struct _EVENT_DESCRIPTOR *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x14003f17c`
- `0x140047798`
- `0x14004bc88`
- `0x14004ff30`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1400500d0`
- `KERNEL32!CreateEventW` at `0x1400500d0`
- `KERNEL32!GetLastError` at `0x1400500e2`
- `KERNEL32!GetLastError` at `0x1400500e2`
- `ole32!CoInitializeSecurity` at `0x140050012`
- `ole32!CoInitializeSecurity` at `0x140050012`
- `ole32!CoInitializeEx` at `0x14004ff7e`
- `ole32!CoInitializeEx` at `0x14004ff7e`

## pseudocode

```c
__int64 __fastcall CWMCService::OnInit(CWMCService *this, struct _EVENT_DESCRIPTOR *a2)
{
  HRESULT v4; // eax
  signed int v5; // ebx
  struct _EVENT_DESCRIPTOR v6; // xmm0
  HRESULT v7; // eax
  const unsigned __int16 *v8; // rdx
  HKEY v9; // rcx
  HANDLE EventW; // rax
  signed int LastError; // eax
  PVOID *v12; // r10
  unsigned int v13; // edi
  unsigned int v15; // [rsp+80h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
  v4 = CoInitializeEx(0, 0);
  v5 = v4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v4 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      66,
      &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
      (unsigned int)v4);
  }
  if ( v5 < 0 )
  {
    v6 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_FAILED_INIT_COINITIALIZE;
LABEL_10:
    *a2 = v6;
LABEL_29:
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_30;
  }
  *((_DWORD *)this + 157) = 1;
  v7 = CoInitializeSecurity(0, -1, 0, 0, 0, 3u, 0, 2u, 0);
  v5 = v7;
  v9 = (HKEY)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v8 = (const unsigned __int16 *)(((v7 >> 31) & 0xFFFFFFFD) + 5);
    if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (unsigned int)v8 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        67,
        &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
        (unsigned int)v7);
  }
  if ( v5 < 0 )
  {
    v6 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_FAILED_INIT_COINITIALIZESECURITY;
    goto LABEL_10;
  }
  *((_DWORD *)this + 34) = 1;
  v15 = 0;
  if ( CheckDWORDRegistryValue(v9, v8, L"EnableDlnaTags", 0, &v15, 0) >= 0 )
  {
    if ( v15 == 1 )
    {
      *((_DWORD *)this + 34) = 0;
    }
    else if ( !v15 )
    {
      *((_DWORD *)this + 34) = 1;
    }
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 80) = EventW;
  if ( EventW )
    goto LABEL_29;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      68,
      &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
      (unsigned int)v5);
    goto LABEL_29;
  }
LABEL_30:
  v13 = (unsigned __int16)v5;
  if ( (v5 & 0x1FFF0000) != 0x70000 )
    v13 = v5;
  if ( v12 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v12 + 28) & 1) != 0
    && *((unsigned __int8 *)v12 + 25) >= (unsigned int)(v13 != 0 ? 2 : 5) )
  {
    WPP_SF_d(v12[2], 69, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, v13);
  }
  return v13;
}

```

## disassembly

```asm
0x14004ff30  mov     [rsp+arg_0], rbx
0x14004ff35  mov     [rsp+arg_8], rsi
0x14004ff3a  push    rdi
0x14004ff3b  push    r12
0x14004ff3d  push    r13
0x14004ff3f  sub     rsp, 50h
0x14004ff43  mov     rsi, rdx
0x14004ff46  mov     rdi, rcx
0x14004ff49  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ff50  lea     r13, WPP_GLOBAL_Control
0x14004ff57  lea     r12, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x14004ff5e  cmp     rcx, r13
0x14004ff61  jz      short loc_14004FF7A
0x14004ff63  test    byte ptr [rcx+1Ch], 1
0x14004ff67  jz      short loc_14004FF7A
0x14004ff69  mov     rcx, [rcx+10h]
0x14004ff6d  mov     edx, 41h ; 'A'
0x14004ff72  mov     r8, r12
0x14004ff75  call    WPP_SF_
0x14004ff7a  xor     edx, edx; dwCoInit
0x14004ff7c  xor     ecx, ecx; pvReserved
0x14004ff7e  call    cs:__imp_CoInitializeEx
0x14004ff84  mov     ebx, eax
0x14004ff86  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ff8d  cmp     rcx, r13
0x14004ff90  jz      short loc_14004FFBF
0x14004ff92  test    byte ptr [rcx+1Ch], 2
0x14004ff96  jz      short loc_14004FFBF
0x14004ff98  mov     edx, eax
0x14004ff9a  movzx   eax, byte ptr [rcx+19h]
0x14004ff9e  sar     edx, 1Fh
0x14004ffa1  and     edx, 0FFFFFFFDh
0x14004ffa4  add     edx, 5
0x14004ffa7  cmp     eax, edx
0x14004ffa9  jb      short loc_14004FFBF
0x14004ffab  mov     rcx, [rcx+10h]
0x14004ffaf  mov     edx, 42h ; 'B'
0x14004ffb4  mov     r9d, ebx
0x14004ffb7  mov     r8, r12
0x14004ffba  call    WPP_SF_d
0x14004ffbf  test    ebx, ebx
0x14004ffc1  jns     short loc_14004FFD3
0x14004ffc3  movups  xmm0, cs:WMC_E_SERVICE_FAILED_INIT_COINITIALIZE
0x14004ffca  movdqu  xmmword ptr [rsi], xmm0
0x14004ffce  jmp     loc_140050125
0x14004ffd3  mov     [rsp+68h+pReserved3], 0; pReserved3
0x14004ffdc  xor     r9d, r9d; pReserved1
0x14004ffdf  mov     [rsp+68h+dwCapabilities], 2; dwCapabilities
0x14004ffe7  xor     r8d, r8d; asAuthSvc
0x14004ffea  mov     [rsp+68h+pAuthList], 0; pAuthList
0x14004fff3  or      edx, 0FFFFFFFFh; cAuthSvc
0x14004fff6  mov     [rsp+68h+dwImpLevel], 3; dwImpLevel
0x14004fffe  xor     ecx, ecx; pSecDesc
0x140050000  mov     [rsp+68h+dwAuthnLevel], 0; dwAuthnLevel
0x140050008  mov     dword ptr [rdi+274h], 1
0x140050012  call    cs:__imp_CoInitializeSecurity
0x140050018  mov     ebx, eax
0x14005001a  mov     rcx, cs:WPP_GLOBAL_Control
0x140050021  cmp     rcx, r13
0x140050024  jz      short loc_140050053
0x140050026  test    byte ptr [rcx+1Ch], 2
0x14005002a  jz      short loc_140050053
0x14005002c  mov     edx, eax
0x14005002e  movzx   eax, byte ptr [rcx+19h]
0x140050032  sar     edx, 1Fh
0x140050035  and     edx, 0FFFFFFFDh
0x140050038  add     edx, 5
0x14005003b  cmp     eax, edx
0x14005003d  jb      short loc_140050053
0x14005003f  mov     rcx, [rcx+10h]
0x140050043  mov     edx, 43h ; 'C'
0x140050048  mov     r9d, ebx
0x14005004b  mov     r8, r12
0x14005004e  call    WPP_SF_d
0x140050053  test    ebx, ebx
0x140050055  jns     short loc_140050063
0x140050057  movups  xmm0, cs:WMC_E_SERVICE_FAILED_INIT_COINITIALIZESECURITY
0x14005005e  jmp     loc_14004FFCA
0x140050063  lea     rax, [rsp+68h+arg_10]
0x14005006b  mov     [rsp+68h+dwImpLevel], 0; int
0x140050073  xor     r9d, r9d; unsigned int
0x140050076  mov     qword ptr [rsp+68h+dwAuthnLevel], rax; unsigned int *
0x14005007b  lea     r8, aEnabledlnatags; "EnableDlnaTags"
0x140050082  mov     dword ptr [rdi+88h], 1
0x14005008c  mov     [rsp+68h+arg_10], 0
0x140050097  call    ?CheckDWORDRegistryValue@@YAJPEAUHKEY__@@PEBG1KAEAKH@Z; CheckDWORDRegistryValue(HKEY__ *,ushort const *,ushort const *,ulong,ulong &,int)
0x14005009c  test    eax, eax
0x14005009e  js      short loc_1400500C6
0x1400500a0  mov     eax, [rsp+68h+arg_10]
0x1400500a7  cmp     eax, 1
0x1400500aa  jnz     short loc_1400500B8
0x1400500ac  mov     dword ptr [rdi+88h], 0
0x1400500b6  jmp     short loc_1400500C6
0x1400500b8  test    eax, eax
0x1400500ba  jnz     short loc_1400500C6
0x1400500bc  mov     dword ptr [rdi+88h], 1
0x1400500c6  xor     r9d, r9d; lpName
0x1400500c9  xor     r8d, r8d; bInitialState
0x1400500cc  xor     edx, edx; bManualReset
0x1400500ce  xor     ecx, ecx; lpEventAttributes
0x1400500d0  call    cs:__imp_CreateEventW
0x1400500d6  mov     [rdi+280h], rax
0x1400500dd  test    rax, rax
0x1400500e0  jnz     short loc_140050125
0x1400500e2  call    cs:__imp_GetLastError
0x1400500e8  mov     ebx, eax
0x1400500ea  test    eax, eax
0x1400500ec  jle     short loc_1400500F7
0x1400500ee  movzx   ebx, ax
0x1400500f1  or      ebx, 80070000h
0x1400500f7  mov     r10, cs:WPP_GLOBAL_Control
0x1400500fe  cmp     r10, r13
0x140050101  jz      short loc_14005012C
0x140050103  test    byte ptr [r10+1Ch], 2
0x140050108  jz      short loc_14005012C
0x14005010a  cmp     byte ptr [r10+19h], 2
0x14005010f  jb      short loc_14005012C
0x140050111  mov     rcx, [r10+10h]
0x140050115  mov     edx, 44h ; 'D'
0x14005011a  mov     r9d, ebx
0x14005011d  mov     r8, r12
0x140050120  call    WPP_SF_d
0x140050125  mov     r10, cs:WPP_GLOBAL_Control
0x14005012c  mov     eax, ebx
0x14005012e  movzx   edi, bx
0x140050131  and     eax, 1FFF0000h
0x140050136  cmp     eax, 70000h
0x14005013b  cmovnz  edi, ebx
0x14005013e  cmp     r10, r13
0x140050141  jz      short loc_140050173
0x140050143  test    byte ptr [r10+1Ch], 1
0x140050148  jz      short loc_140050173
0x14005014a  movzx   ecx, byte ptr [r10+19h]
0x14005014f  mov     eax, edi
0x140050151  neg     eax
0x140050153  sbb     edx, edx
0x140050155  and     edx, 0FFFFFFFDh
0x140050158  add     edx, 5
0x14005015b  cmp     ecx, edx
0x14005015d  jb      short loc_140050173
0x14005015f  mov     rcx, [r10+10h]
0x140050163  mov     edx, 45h ; 'E'
0x140050168  mov     r9d, edi
0x14005016b  mov     r8, r12
0x14005016e  call    WPP_SF_d
0x140050173  mov     rbx, [rsp+68h+arg_0]
0x140050178  mov     eax, edi
0x14005017a  mov     rsi, [rsp+68h+arg_8]
0x14005017f  add     rsp, 50h
0x140050183  pop     r13
0x140050185  pop     r12
0x140050187  pop     rdi
0x140050188  retn
```
