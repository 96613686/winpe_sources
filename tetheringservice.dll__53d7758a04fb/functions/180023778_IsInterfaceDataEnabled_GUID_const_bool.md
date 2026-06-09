# IsInterfaceDataEnabled(_GUID const *,bool *)

- ea: `0x180023778`
- end: `0x18002396c`
- name: `?IsInterfaceDataEnabled@@YAJPEBU_GUID@@PEA_N@Z`
- size: `500`
- prototype: `__int64 __fastcall(const struct _GUID *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000ffe4`

## callees

- `0x1800035a8`
- `0x18000bf74`
- `0x180023778`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800237d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800237d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800237e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800237e8`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180023845`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180023845`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x1800237e0`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180023959`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x1800237e0`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180023959`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18002393f`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18002393f`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180023803`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180023803`

## pseudocode

```c
__int64 __fastcall IsInterfaceDataEnabled(const struct _GUID *a1, bool *a2)
{
  _DWORD *v3; // rcx
  DWORD LastError; // ebx
  unsigned int Interface; // ebx
  TetheringServiceTelemetry *v7; // rcx
  __int64 v8; // rdx
  int v9; // edx
  __int64 v11; // [rsp+40h] [rbp-10h] BYREF
  int v12; // [rsp+80h] [rbp+30h] BYREF
  int v13; // [rsp+90h] [rbp+40h]
  _DWORD *v14; // [rsp+98h] [rbp+48h]

  v11 = -1;
  v3 = 0;
  v13 = 0;
  v12 = 0;
  v14 = 0;
  if ( !a1 || !a2 )
  {
    Interface = -2147024809;
    goto LABEL_30;
  }
  *a2 = 0;
  if ( !(unsigned __int8)IsWwanOpenHandlePresent() )
  {
    Interface = 50;
LABEL_22:
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_26;
    }
    v8 = 58;
    goto LABEL_25;
  }
  if ( v11 != -1 )
  {
    LastError = GetLastError();
    WwanCloseHandle(v11, 0);
    SetLastError(LastError);
  }
  v11 = -1;
  Interface = WwanOpenHandle(1, 0, &v12, &v11);
  if ( Interface )
    goto LABEL_22;
  Interface = WwanQueryInterface(v11, a1, 15);
  if ( Interface )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_26;
    }
    v8 = 59;
LABEL_25:
    WPP_SF_d(*((_QWORD *)v7 + 2), v8, &WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids, Interface);
LABEL_26:
    if ( (int)Interface > 0 )
      Interface = (unsigned __int16)Interface | 0x80070000;
    v3 = v14;
    goto LABEL_30;
  }
  v3 = v14;
  Interface = 0;
  if ( *v14 )
  {
    v9 = *v14 - 1;
    if ( v9 >= 0 )
    {
      while ( (*(_QWORD *)&v14[5 * v9 + 1] != WWAN_PROFILE_SET_GUID_INTERNET_AO
            || *(_QWORD *)&v14[5 * v9 + 3] != 0x5F5157C6F13398A1LL)
           && (*(_QWORD *)&v14[5 * v9 + 1] != WWAN_PROFILE_SET_GUID_ALL_HOST_PROFILES
            || *(_QWORD *)&v14[5 * v9 + 3] != 0x5770A73BA7DDA38FLL) )
      {
        if ( v9 )
        {
          if ( --v9 >= 0 )
            continue;
        }
        goto LABEL_30;
      }
      *a2 = v14[5 * v9 + 5] == 1;
    }
  }
LABEL_30:
  if ( v3 )
  {
    WwanFreeMemory(v3);
    v14 = 0;
  }
  if ( v11 != -1 )
    WwanCloseHandle(v11, 0);
  return Interface;
}

```

## disassembly

```asm
0x180023778  push    rbp
0x18002377a  push    rbx
0x18002377b  push    rsi
0x18002377c  push    rdi
0x18002377d  push    r14
0x18002377f  mov     rbp, rsp
0x180023782  sub     rsp, 50h
0x180023786  mov     r14, rcx
0x180023789  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFFh
0x180023791  xor     ecx, ecx
0x180023793  mov     [rbp+arg_10], 0
0x18002379a  mov     [rbp+arg_0], 0
0x1800237a1  mov     rsi, rdx
0x1800237a4  mov     [rbp+arg_18], rcx
0x1800237a8  test    r14, r14
0x1800237ab  jz      loc_180023935
0x1800237b1  test    rdx, rdx
0x1800237b4  jz      loc_180023935
0x1800237ba  mov     [rdx], cl
0x1800237bc  call    IsWwanOpenHandlePresent
0x1800237c1  test    al, al
0x1800237c3  jz      loc_1800238EC
0x1800237c9  mov     rdi, [rbp+var_10]
0x1800237cd  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800237d1  jz      short loc_1800237EE
0x1800237d3  call    cs:__imp_GetLastError
0x1800237d9  xor     edx, edx
0x1800237db  mov     rcx, rdi
0x1800237de  mov     ebx, eax
0x1800237e0  call    cs:__imp_WwanCloseHandle
0x1800237e6  mov     ecx, ebx; dwErrCode
0x1800237e8  call    cs:__imp_SetLastError
0x1800237ee  xor     edx, edx
0x1800237f0  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFFh
0x1800237f8  lea     r9, [rbp+var_10]
0x1800237fc  lea     r8, [rbp+arg_0]
0x180023800  lea     ecx, [rdx+1]
0x180023803  call    cs:__imp_WwanOpenHandle
0x180023809  mov     ebx, eax
0x18002380b  test    eax, eax
0x18002380d  jnz     loc_1800238F1
0x180023813  mov     rcx, [rbp+var_10]
0x180023817  lea     rax, [rbp+arg_18]
0x18002381b  mov     [rsp+50h+var_18], 0
0x180023824  lea     r8d, [rbx+0Fh]
0x180023828  mov     [rsp+50h+var_20], 0
0x180023831  xor     r9d, r9d
0x180023834  mov     [rsp+50h+var_28], rax
0x180023839  mov     rdx, r14
0x18002383c  lea     rax, [rbp+arg_10]
0x180023840  mov     [rsp+50h+var_30], rax
0x180023845  call    cs:__imp_WwanQueryInterface
0x18002384b  mov     ebx, eax
0x18002384d  test    eax, eax
0x18002384f  jz      short loc_18002387C
0x180023851  mov     rcx, cs:WPP_GLOBAL_Control
0x180023858  lea     rax, WPP_GLOBAL_Control
0x18002385f  cmp     rcx, rax
0x180023862  jz      loc_180023922
0x180023868  test    byte ptr [rcx+1Ch], 1
0x18002386c  jz      loc_180023922
0x180023872  mov     edx, 3Bh ; ';'
0x180023877  jmp     loc_18002390F
0x18002387c  mov     rcx, [rbp+arg_18]
0x180023880  xor     ebx, ebx
0x180023882  mov     edx, [rcx]
0x180023884  test    edx, edx
0x180023886  jz      loc_18002393A
0x18002388c  sub     edx, 1
0x18002388f  js      loc_18002393A
0x180023895  mov     r10, cs:qword_1800365B0
0x18002389c  mov     rdi, cs:WWAN_PROFILE_SET_GUID_INTERNET_AO
0x1800238a3  mov     r9, cs:qword_1800365D0
0x1800238aa  mov     r11, cs:WWAN_PROFILE_SET_GUID_ALL_HOST_PROFILES
0x1800238b1  movsxd  rax, edx
0x1800238b4  lea     r8, [rax+rax*4]
0x1800238b8  cmp     [rcx+r8*4+4], rdi
0x1800238bd  jnz     short loc_1800238C6
0x1800238bf  cmp     [rcx+r8*4+0Ch], r10
0x1800238c4  jz      short loc_1800238DF
0x1800238c6  cmp     [rcx+r8*4+4], r11
0x1800238cb  jnz     short loc_1800238D4
0x1800238cd  cmp     [rcx+r8*4+0Ch], r9
0x1800238d2  jz      short loc_1800238DF
0x1800238d4  test    edx, edx
0x1800238d6  jz      short loc_18002393A
0x1800238d8  sub     edx, 1
0x1800238db  jns     short loc_1800238B1
0x1800238dd  jmp     short loc_18002393A
0x1800238df  cmp     dword ptr [rcx+r8*4+14h], 1
0x1800238e5  setz    al
0x1800238e8  mov     [rsi], al
0x1800238ea  jmp     short loc_18002393A
0x1800238ec  mov     ebx, 32h ; '2'
0x1800238f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800238f8  lea     rax, WPP_GLOBAL_Control
0x1800238ff  cmp     rcx, rax
0x180023902  jz      short loc_180023922
0x180023904  test    byte ptr [rcx+1Ch], 1
0x180023908  jz      short loc_180023922
0x18002390a  mov     edx, 3Ah ; ':'
0x18002390f  mov     rcx, [rcx+10h]
0x180023913  lea     r8, WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids
0x18002391a  mov     r9d, ebx
0x18002391d  call    WPP_SF_d
0x180023922  test    ebx, ebx
0x180023924  jle     short loc_18002392F
0x180023926  movzx   ebx, bx
0x180023929  or      ebx, 80070000h
0x18002392f  mov     rcx, [rbp+arg_18]
0x180023933  jmp     short loc_18002393A
0x180023935  mov     ebx, 80070057h
0x18002393a  test    rcx, rcx
0x18002393d  jz      short loc_18002394D
0x18002393f  call    cs:__imp_WwanFreeMemory
0x180023945  mov     [rbp+arg_18], 0
0x18002394d  mov     rcx, [rbp+var_10]
0x180023951  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180023955  jz      short loc_18002395F
0x180023957  xor     edx, edx
0x180023959  call    cs:__imp_WwanCloseHandle
0x18002395f  mov     eax, ebx
0x180023961  add     rsp, 50h
0x180023965  pop     r14
0x180023967  pop     rdi
0x180023968  pop     rsi
0x180023969  pop     rbx
0x18002396a  pop     rbp
0x18002396b  retn
```
