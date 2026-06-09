# CFUSManager::StoreFUSTarget(ulong,_WINBIO_IDENTITY *,unsigned __int64,_FILETIME *)

- ea: `0x18006fac4`
- end: `0x18006fc88`
- name: `?StoreFUSTarget@CFUSManager@@QEAAJKPEAU_WINBIO_IDENTITY@@_KPEAU_FILETIME@@@Z`
- size: `452`
- prototype: `int(CFUSManager *__hidden this, unsigned int, struct _WINBIO_IDENTITY *, unsigned __int64, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x180060a78`

## callees

- `0x18001434c`
- `0x180014854`
- `0x180014bcc`
- `0x180068f60`
- `0x180069cc8`
- `0x18006a53c`
- `0x18006f8c0`
- `0x18006fac4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fb4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fb4f`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18006fb45`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18006fb45`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18006fb85`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18006fb85`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18006fba3`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18006fba3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall CFUSManager::StoreFUSTarget(
        CFUSManager *this,
        DWORD a2,
        struct _WINBIO_IDENTITY *a3,
        __int64 a4,
        struct _FILETIME *a5)
{
  void *v8; // r14
  __int64 v9; // rcx
  int result; // eax
  __int128 v11; // xmm6
  __int128 v12; // xmm7
  __int128 v13; // xmm8
  DWORD pSessionId[2]; // [rsp+38h] [rbp-D0h] BYREF
  LPWSTR ppBuffer; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE v16[16]; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v17[48]; // [rsp+58h] [rbp-B0h] BYREF
  __m256i v18; // [rsp+88h] [rbp-80h]
  __int128 v19; // [rsp+A8h] [rbp-60h]
  _BYTE v20[32]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v21[32]; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v22; // [rsp+F8h] [rbp-10h]
  __int128 v23; // [rsp+108h] [rbp+0h]
  __int128 v24; // [rsp+118h] [rbp+10h]
  __m256i v25; // [rsp+128h] [rbp+20h]
  __int128 v26; // [rsp+148h] [rbp+40h]

  v8 = g_FUS_Manager;
  ppBuffer = 0;
  pSessionId[1] = 0;
  pSessionId[0] = 0;
  if ( !(unsigned __int8)IsWTSFreeMemoryPresent(this) || !(unsigned __int8)IsWTSFreeMemoryPresent(v9) )
    return -2147467263;
  if ( ProcessIdToSessionId(a2, pSessionId)
    && WTSQuerySessionInformationW(0, pSessionId[0], WTSWinStationName, &ppBuffer, &pSessionId[1]) )
  {
    std::wstring::wstring((__int64)v20, (__int64)ppBuffer);
    WTSFreeMemory(ppBuffer);
    memset_0(v17, 0, 0x50u);
    v11 = *(_OWORD *)&a3->Type;
    v12 = *(_OWORD *)&a3->Value.AccountSid.Data[8];
    v13 = *(_OWORD *)&a3->Value.AccountSid.Data[24];
    *(_OWORD *)v18.m256i_i8 = *(_OWORD *)&a3->Value.AccountSid.Data[40];
    *(_OWORD *)((char *)&v18.m256i_u64[1] + 4) = *(_OWORD *)&a3->Value.AccountSid.Data[52];
    *(_QWORD *)&v19 = a4;
    *((struct _FILETIME *)&v19 + 1) = *a5;
    std::wstring::wstring(v21, v20);
    v22 = v11;
    v23 = v12;
    v24 = v13;
    v25 = v18;
    v26 = v19;
    std::_Tree<std::_Tmap_traits<std::wstring,_WINBIO_FUS_EVENT,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_WINBIO_FUS_EVENT>>,0>>::_Emplace<std::pair<std::wstring,_WINBIO_FUS_EVENT>>(
      v8,
      v16,
      v21);
    std::wstring::_Tidy_deallocate(v21);
    std::wstring::_Tidy_deallocate(v20);
    if ( v16[8] )
      return 0;
    else
      return -2147467259;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18006fac4  mov     rax, rsp
0x18006fac7  mov     [rax+8], rbx
0x18006facb  mov     [rax+18h], rsi
0x18006facf  push    rbp
0x18006fad0  push    rdi
0x18006fad1  push    r14
0x18006fad3  lea     rbp, [rax-0A8h]
0x18006fada  sub     rsp, 190h
0x18006fae1  movaps  xmmword ptr [rax-28h], xmm6
0x18006fae5  movaps  xmmword ptr [rax-38h], xmm7
0x18006fae9  movaps  xmmword ptr [rax-48h], xmm8
0x18006faee  mov     rax, cs:__security_cookie
0x18006faf5  xor     rax, rsp
0x18006faf8  mov     [rbp+0A0h+var_50], rax
0x18006fafc  mov     rsi, r9
0x18006faff  mov     rdi, r8
0x18006fb02  mov     ebx, edx
0x18006fb04  mov     r14, cs:?g_FUS_Manager@@3PEAVCFUSManager@@EA; CFUSManager * g_FUS_Manager
0x18006fb0b  mov     [rsp+1A0h+ppBuffer], 0
0x18006fb14  mov     [rsp+1A0h+pSessionId+4], 0
0x18006fb1c  mov     [rsp+1A0h+pSessionId], 0
0x18006fb24  call    IsWTSFreeMemoryPresent
0x18006fb29  test    al, al
0x18006fb2b  jz      loc_18006FC50
0x18006fb31  call    IsWTSFreeMemoryPresent
0x18006fb36  test    al, al
0x18006fb38  jz      loc_18006FC50
0x18006fb3e  lea     rdx, [rsp+1A0h+pSessionId]; pSessionId
0x18006fb43  mov     ecx, ebx; dwProcessId
0x18006fb45  call    cs:__imp_ProcessIdToSessionId
0x18006fb4b  test    eax, eax
0x18006fb4d  jnz     short loc_18006FB6A
0x18006fb4f  call    cs:__imp_GetLastError
0x18006fb55  test    eax, eax
0x18006fb57  jle     loc_18006FC55
0x18006fb5d  movzx   eax, ax
0x18006fb60  or      eax, 80070000h
0x18006fb65  jmp     loc_18006FC55
0x18006fb6a  lea     rax, [rsp+1A0h+pSessionId+4]
0x18006fb6f  mov     [rsp+1A0h+pBytesReturned], rax; pBytesReturned
0x18006fb74  lea     r9, [rsp+1A0h+ppBuffer]; ppBuffer
0x18006fb79  mov     r8d, 6; WTSInfoClass
0x18006fb7f  mov     edx, [rsp+1A0h+pSessionId]; SessionId
0x18006fb83  xor     ecx, ecx; hServer
0x18006fb85  call    cs:__imp_WTSQuerySessionInformationW
0x18006fb8b  test    eax, eax
0x18006fb8d  jz      short loc_18006FB4F
0x18006fb8f  mov     rdx, [rsp+1A0h+ppBuffer]
0x18006fb94  lea     rcx, [rbp+0A0h+var_F0]
0x18006fb98  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006fb9d  nop
0x18006fb9e  mov     rcx, [rsp+1A0h+ppBuffer]; pMemory
0x18006fba3  call    cs:__imp_WTSFreeMemory
0x18006fba9  xor     edx, edx; Val
0x18006fbab  lea     r8d, [rdx+50h]; Size
0x18006fbaf  lea     rcx, [rsp+1A0h+var_150]; void *
0x18006fbb4  call    memset_0
0x18006fbb9  movups  xmm6, xmmword ptr [rdi]
0x18006fbbc  movups  xmm7, xmmword ptr [rdi+10h]
0x18006fbc0  movups  xmm8, xmmword ptr [rdi+20h]
0x18006fbc5  movups  xmm0, xmmword ptr [rdi+30h]
0x18006fbc9  movaps  [rbp+0A0h+var_120], xmm0
0x18006fbcd  movups  xmm1, xmmword ptr [rdi+3Ch]
0x18006fbd1  movups  [rbp+0A0h+var_120+0Ch], xmm1
0x18006fbd5  mov     qword ptr [rbp+0A0h+var_100], rsi
0x18006fbd9  mov     rax, [rbp+0A0h+arg_20]
0x18006fbe0  mov     rcx, [rax]
0x18006fbe3  mov     qword ptr [rbp+0A0h+var_100+8], rcx
0x18006fbe7  lea     rdx, [rbp+0A0h+var_F0]
0x18006fbeb  lea     rcx, [rbp+0A0h+var_D0]
0x18006fbef  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006fbf4  movaps  [rbp+0A0h+var_B0], xmm6
0x18006fbf8  movaps  [rbp+0A0h+var_A0], xmm7
0x18006fbfc  movaps  [rbp+0A0h+var_90], xmm8
0x18006fc01  movaps  xmm0, [rbp+0A0h+var_120]
0x18006fc05  movaps  [rbp+0A0h+var_80], xmm0
0x18006fc09  movaps  xmm1, [rbp+0A0h+var_110]
0x18006fc0d  movaps  [rbp+0A0h+var_70], xmm1
0x18006fc11  movaps  xmm0, [rbp+0A0h+var_100]
0x18006fc15  movaps  [rbp+0A0h+var_60], xmm0
0x18006fc19  lea     r8, [rbp+0A0h+var_D0]
0x18006fc1d  lea     rdx, [rsp+1A0h+var_160]
0x18006fc22  mov     rcx, r14
0x18006fc25  call    ??$_Emplace@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WINBIO_FUS_EVENT@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WINBIO_FUS_EVENT@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WINBIO_FUS_EVENT@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WINBIO_FUS_EVENT@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WINBIO_FUS_EVENT@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,_WINBIO_FUS_EVENT,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_WINBIO_FUS_EVENT>>,0>>::_Emplace<std::pair<std::wstring,_WINBIO_FUS_EVENT>>(std::pair<std::wstring,_WINBIO_FUS_EVENT> &&)
0x18006fc2a  nop
0x18006fc2b  lea     rcx, [rbp+0A0h+var_D0]
0x18006fc2f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006fc34  nop
0x18006fc35  lea     rcx, [rbp+0A0h+var_F0]
0x18006fc39  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006fc3e  cmp     [rsp+1A0h+var_158], 0
0x18006fc43  jz      short loc_18006FC49
0x18006fc45  xor     eax, eax
0x18006fc47  jmp     short loc_18006FC55
0x18006fc49  mov     eax, 80004005h
0x18006fc4e  jmp     short loc_18006FC55
0x18006fc50  mov     eax, 80004001h
0x18006fc55  mov     rcx, [rbp+0A0h+var_50]
0x18006fc59  xor     rcx, rsp; StackCookie
0x18006fc5c  call    __security_check_cookie
0x18006fc61  lea     r11, [rsp+1A0h+var_10]
0x18006fc69  mov     rbx, [r11+20h]
0x18006fc6d  mov     rsi, [r11+30h]
0x18006fc71  movaps  xmm6, xmmword ptr [r11-10h]
0x18006fc76  movaps  xmm7, xmmword ptr [r11-20h]
0x18006fc7b  movaps  xmm8, xmmword ptr [r11-30h]
0x18006fc80  mov     rsp, r11
0x18006fc83  pop     r14
0x18006fc85  pop     rdi
0x18006fc86  pop     rbp
0x18006fc87  retn
```
