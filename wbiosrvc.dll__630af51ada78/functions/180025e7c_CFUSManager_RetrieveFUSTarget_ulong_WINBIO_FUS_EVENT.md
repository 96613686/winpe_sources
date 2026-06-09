# CFUSManager::RetrieveFUSTarget(ulong,_WINBIO_FUS_EVENT *)

- ea: `0x180025e7c`
- end: `0x18002603a`
- name: `?RetrieveFUSTarget@CFUSManager@@QEAAJKPEAU_WINBIO_FUS_EVENT@@@Z`
- size: `446`
- prototype: `int(CFUSManager *__hidden this, unsigned int, struct _WINBIO_FUS_EVENT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180025bc0`

## callees

- `0x180014854`
- `0x1800148b4`
- `0x180014938`
- `0x180014ed8`
- `0x180025e7c`
- `0x180027c7c`
- `0x180068f60`
- `0x18006a53c`
- `0x18006f9d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025eee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025eee`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180025ee4`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180025ee4`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x180025f21`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x180025f21`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180025f56`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180025f56`

## pseudocode

```c
int __fastcall CFUSManager::RetrieveFUSTarget(CFUSManager *this, DWORD a2, struct _WINBIO_FUS_EVENT *a3)
{
  __int64 **v3; // r14
  __int64 v6; // rcx
  int result; // eax
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 *v10; // rdi
  __int64 *i; // rbx
  __int64 v12; // rax
  __int64 v13; // rcx
  DWORD pSessionId; // [rsp+30h] [rbp-50h] BYREF
  DWORD pBytesReturned; // [rsp+34h] [rbp-4Ch] BYREF
  LPWSTR ppBuffer; // [rsp+38h] [rbp-48h] BYREF
  int v17; // [rsp+4Ch] [rbp-34h]
  _OWORD v18[2]; // [rsp+58h] [rbp-28h] BYREF

  v3 = (__int64 **)g_FUS_Manager;
  ppBuffer = 0;
  pBytesReturned = 0;
  pSessionId = 0;
  if ( !(unsigned __int8)IsWTSFreeMemoryPresent(this) || !(unsigned __int8)IsWTSFreeMemoryPresent(v6) )
    return -2147467263;
  if ( ProcessIdToSessionId(a2, &pSessionId)
    && WTSQuerySessionInformationW(0, pSessionId, WTSWinStationName, &ppBuffer, &pBytesReturned) )
  {
    memset(v18, 0, sizeof(v18));
    v8 = std::_WChar_traits<unsigned short>::length(ppBuffer);
    std::wstring::_Construct<1,unsigned short const *>(v18, v9, v8);
    WTSFreeMemory(ppBuffer);
    v10 = *v3;
    v17 = 0;
    for ( i = (__int64 *)v10[1]; !*((_BYTE *)i + 25); i = (__int64 *)*i )
    {
      if ( (int)std::wstring::compare(i + 4, v18) >= 0 )
        v10 = i;
      else
        i += 2;
    }
    if ( *((_BYTE *)v10 + 25) || (int)std::wstring::compare(v18, v10 + 4) < 0 || v10 == *v3 )
    {
      std::wstring::_Tidy_deallocate(v18);
      return -2147024894;
    }
    else
    {
      *(_OWORD *)a3 = *((_OWORD *)v10 + 4);
      *((_OWORD *)a3 + 1) = *((_OWORD *)v10 + 5);
      *((_OWORD *)a3 + 2) = *((_OWORD *)v10 + 6);
      *((_OWORD *)a3 + 3) = *((_OWORD *)v10 + 7);
      *((_OWORD *)a3 + 4) = *((_OWORD *)v10 + 8);
      *((_OWORD *)a3 + 5) = *((_OWORD *)v10 + 9);
      v12 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,_WINBIO_FUS_EVENT>>>::_Extract(v3, v10);
      std::_Tree_node<std::pair<std::wstring const,_WINBIO_FUS_EVENT>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<std::wstring const,_WINBIO_FUS_EVENT>,void *>>>(
        v13,
        v12);
      std::wstring::_Tidy_deallocate(v18);
      return 0;
    }
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
0x180025e7c  mov     [rsp-18h+arg_0], rbx
0x180025e81  mov     [rsp-18h+arg_18], rsi
0x180025e86  push    rbp
0x180025e87  push    rdi
0x180025e88  push    r14
0x180025e8a  mov     rbp, rsp
0x180025e8d  sub     rsp, 80h
0x180025e94  mov     rax, cs:__security_cookie
0x180025e9b  xor     rax, rsp
0x180025e9e  mov     [rbp+var_8], rax
0x180025ea2  mov     r14, cs:?g_FUS_Manager@@3PEAVCFUSManager@@EA; CFUSManager * g_FUS_Manager
0x180025ea9  mov     rsi, r8
0x180025eac  mov     ebx, edx
0x180025eae  mov     [rbp+ppBuffer], 0
0x180025eb6  mov     [rbp+var_4C], 0
0x180025ebd  mov     [rbp+pSessionId], 0
0x180025ec4  call    IsWTSFreeMemoryPresent
0x180025ec9  test    al, al
0x180025ecb  jz      loc_180026011
0x180025ed1  call    IsWTSFreeMemoryPresent
0x180025ed6  test    al, al
0x180025ed8  jz      loc_180026011
0x180025ede  lea     rdx, [rbp+pSessionId]; pSessionId
0x180025ee2  mov     ecx, ebx; dwProcessId
0x180025ee4  call    cs:__imp_ProcessIdToSessionId
0x180025eea  test    eax, eax
0x180025eec  jnz     short loc_180025F09
0x180025eee  call    cs:__imp_GetLastError
0x180025ef4  test    eax, eax
0x180025ef6  jle     loc_180026016
0x180025efc  movzx   eax, ax
0x180025eff  or      eax, 80070000h
0x180025f04  jmp     loc_180026016
0x180025f09  mov     edx, [rbp+pSessionId]; SessionId
0x180025f0c  lea     rax, [rbp+var_4C]
0x180025f10  lea     r9, [rbp+ppBuffer]; ppBuffer
0x180025f14  mov     [rsp+80h+pBytesReturned], rax; pBytesReturned
0x180025f19  mov     r8d, 6; WTSInfoClass
0x180025f1f  xor     ecx, ecx; hServer
0x180025f21  call    cs:__imp_WTSQuerySessionInformationW
0x180025f27  test    eax, eax
0x180025f29  jz      short loc_180025EEE
0x180025f2b  mov     rcx, [rbp+ppBuffer]
0x180025f2f  xorps   xmm0, xmm0
0x180025f32  xorps   xmm1, xmm1
0x180025f35  movups  [rbp+var_28], xmm0
0x180025f39  movdqu  [rbp+var_18], xmm1
0x180025f3e  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180025f43  mov     rdx, rcx
0x180025f46  mov     r8, rax
0x180025f49  lea     rcx, [rbp+var_28]
0x180025f4d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180025f52  mov     rcx, [rbp+ppBuffer]; pMemory
0x180025f56  call    cs:__imp_WTSFreeMemory
0x180025f5c  mov     rdi, [r14]
0x180025f5f  xor     eax, eax
0x180025f61  mov     [rbp+var_34], eax
0x180025f64  mov     rbx, [rdi+8]
0x180025f68  cmp     [rbx+19h], al
0x180025f6b  jnz     short loc_180025F90
0x180025f6d  lea     rcx, [rbx+20h]
0x180025f71  lea     rdx, [rbp+var_28]
0x180025f75  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHAEBV12@@Z; std::wstring::compare(std::wstring const &)
0x180025f7a  test    eax, eax
0x180025f7c  jns     short loc_180025F84
0x180025f7e  add     rbx, 10h
0x180025f82  jmp     short loc_180025F87
0x180025f84  mov     rdi, rbx
0x180025f87  mov     rbx, [rbx]
0x180025f8a  cmp     byte ptr [rbx+19h], 0
0x180025f8e  jz      short loc_180025F6D
0x180025f90  cmp     byte ptr [rdi+19h], 0
0x180025f94  jnz     short loc_180026001
0x180025f96  lea     rdx, [rdi+20h]
0x180025f9a  lea     rcx, [rbp+var_28]
0x180025f9e  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHAEBV12@@Z; std::wstring::compare(std::wstring const &)
0x180025fa3  test    eax, eax
0x180025fa5  js      short loc_180026001
0x180025fa7  cmp     rdi, [r14]
0x180025faa  jz      short loc_180026001
0x180025fac  movups  xmm0, xmmword ptr [rdi+40h]
0x180025fb0  mov     rdx, rdi
0x180025fb3  mov     rcx, r14
0x180025fb6  movaps  xmmword ptr [rsi], xmm0
0x180025fb9  movups  xmm1, xmmword ptr [rdi+50h]
0x180025fbd  movaps  xmmword ptr [rsi+10h], xmm1
0x180025fc1  movups  xmm0, xmmword ptr [rdi+60h]
0x180025fc5  movaps  xmmword ptr [rsi+20h], xmm0
0x180025fc9  movups  xmm1, xmmword ptr [rdi+70h]
0x180025fcd  movaps  xmmword ptr [rsi+30h], xmm1
0x180025fd1  movups  xmm0, xmmword ptr [rdi+80h]
0x180025fd8  movaps  xmmword ptr [rsi+40h], xmm0
0x180025fdc  movups  xmm1, xmmword ptr [rdi+90h]
0x180025fe3  movaps  xmmword ptr [rsi+50h], xmm1
0x180025fe7  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WINBIO_FUS_EVENT@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WINBIO_FUS_EVENT@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WINBIO_FUS_EVENT@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,_WINBIO_FUS_EVENT>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,_WINBIO_FUS_EVENT>>>,std::_Iterator_base0>)
0x180025fec  mov     rdx, rax
0x180025fef  call    ??$_Freenode@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WINBIO_FUS_EVENT@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WINBIO_FUS_EVENT@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WINBIO_FUS_EVENT@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_Tree_node<std::pair<std::wstring const,_WINBIO_FUS_EVENT>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<std::wstring const,_WINBIO_FUS_EVENT>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,_WINBIO_FUS_EVENT>,void *>> &,std::_Tree_node<std::pair<std::wstring const,_WINBIO_FUS_EVENT>,void *> *)
0x180025ff4  lea     rcx, [rbp+var_28]
0x180025ff8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025ffd  xor     eax, eax
0x180025fff  jmp     short loc_180026016
0x180026001  lea     rcx, [rbp+var_28]
0x180026005  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002600a  mov     eax, 80070002h
0x18002600f  jmp     short loc_180026016
0x180026011  mov     eax, 80004001h
0x180026016  mov     rcx, [rbp+var_8]
0x18002601a  xor     rcx, rsp; StackCookie
0x18002601d  call    __security_check_cookie
0x180026022  lea     r11, [rsp+80h+var_s0]
0x18002602a  mov     rbx, [r11+20h]
0x18002602e  mov     rsi, [r11+38h]
0x180026032  mov     rsp, r11
0x180026035  pop     r14
0x180026037  pop     rdi
0x180026038  pop     rbp
0x180026039  retn
```
