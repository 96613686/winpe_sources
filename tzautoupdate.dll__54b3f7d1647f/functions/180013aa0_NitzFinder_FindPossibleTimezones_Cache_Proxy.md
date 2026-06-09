# NitzFinder::FindPossibleTimezones(Cache::Proxy &)

- ea: `0x180013aa0`
- end: `0x180013c46`
- name: `?FindPossibleTimezones@NitzFinder@@UEAA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAVProxy@Cache@@@Z`
- size: `422`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18000da78`
- `0x18000e25c`
- `0x18000e968`
- `0x18000e9cc`
- `0x1800135b0`
- `0x180013aa0`
- `0x180013c4c`
- `0x180013de0`
- `0x18001b0f6`
- `0x18001b150`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!EnumDynamicTimeZoneInformation` at `0x180013b2f`
- `api-ms-win-core-timezone-l1-1-0!EnumDynamicTimeZoneInformation` at `0x180013bbf`
- `api-ms-win-core-timezone-l1-1-0!EnumDynamicTimeZoneInformation` at `0x180013b2f`
- `api-ms-win-core-timezone-l1-1-0!EnumDynamicTimeZoneInformation` at `0x180013bbf`

## pseudocode

```c
_QWORD *__fastcall NitzFinder::FindPossibleTimezones(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v5; // r14
  unsigned int v6; // edi
  int v7; // ebx
  int v8; // r14d
  __int64 v9; // rdi
  __int64 v10; // rbx
  int v12[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v13; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v14; // [rsp+38h] [rbp-C8h]
  _QWORD v15[5]; // [rsp+48h] [rbp-B8h] BYREF
  struct _TIME_DYNAMIC_ZONE_INFORMATION v16; // [rsp+70h] [rbp-90h] BYREF

  *(_QWORD *)v12 = a2;
  if ( *(_BYTE *)(*(_QWORD *)(a3 + 96) + 4LL) )
  {
    v13 = 0;
    v5 = 0;
    v14 = 0;
    memset_0(&v16, 0, sizeof(v16));
    v6 = 0;
    if ( !(unsigned int)EnumDynamicTimeZoneInformation(0, &v16) )
    {
      do
      {
        v12[0] = 0;
        if ( (int)GetEffectiveOffset(&v16, v12) >= 0 )
        {
          v7 = v12[0];
          v8 = v12[0] + v16.Bias;
          if ( *(_DWORD *)Cache::ValueProxy<int>::GetValue(a3 + 96) == v7
            && (!*(_BYTE *)(*(_QWORD *)(a3 + 112) + 4LL) || *(_DWORD *)Cache::ValueProxy<int>::GetValue(a3 + 112) == v8) )
          {
            std::wstring::wstring(v15, v16.TimeZoneKeyName);
            std::vector<std::wstring>::push_back(&v13, v15);
            std::wstring::_Tidy(v15, 1, 0);
          }
        }
        ++v6;
      }
      while ( !(unsigned int)EnumDynamicTimeZoneInformation(v6, &v16) );
      v5 = v14;
    }
    v9 = *((_QWORD *)&v13 + 1);
    v10 = v13;
    std::_Sort<std::wstring *,__int64>(v13, *((_QWORD *)&v13 + 1), (__int64)(*((_QWORD *)&v13 + 1) - v13) >> 5);
    *a2 = v10;
    a2[1] = v9;
    a2[2] = v5;
    v13 = 0;
    v14 = 0;
    std::vector<std::wstring>::_Tidy(&v13);
  }
  else
  {
    *a2 = 0;
    a2[1] = 0;
    a2[2] = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x180013aa0  mov     [rsp-8+arg_0], rbx
0x180013aa5  mov     [rsp-8+arg_10], rsi
0x180013aaa  push    rbp
0x180013aab  push    rdi
0x180013aac  push    r12
0x180013aae  push    r14
0x180013ab0  push    r15
0x180013ab2  lea     rbp, [rsp-130h]
0x180013aba  sub     rsp, 230h
0x180013ac1  mov     rax, cs:__security_cookie
0x180013ac8  xor     rax, rsp
0x180013acb  mov     [rbp+150h+var_30], rax
0x180013ad2  mov     r15, r8
0x180013ad5  mov     rsi, rdx
0x180013ad8  mov     qword ptr [rsp+250h+var_230], rdx
0x180013add  mov     rcx, [r8+60h]
0x180013ae1  cmp     byte ptr [rcx+4], 0
0x180013ae5  jnz     short loc_180013B03
0x180013ae7  mov     qword ptr [rdx], 0
0x180013aee  mov     qword ptr [rdx+8], 0
0x180013af6  mov     qword ptr [rdx+10h], 0
0x180013afe  jmp     loc_180013C18
0x180013b03  xorps   xmm0, xmm0
0x180013b06  movdqu  [rsp+250h+var_228], xmm0
0x180013b0c  xor     r14d, r14d
0x180013b0f  mov     [rsp+250h+var_218], r14
0x180013b14  xor     edx, edx; Val
0x180013b16  mov     r8d, 1B0h; Size
0x180013b1c  lea     rcx, [rsp+250h+var_1E0]; void *
0x180013b21  call    memset_0
0x180013b26  xor     edi, edi
0x180013b28  lea     rdx, [rsp+250h+var_1E0]
0x180013b2d  xor     ecx, ecx
0x180013b2f  call    cs:__imp_EnumDynamicTimeZoneInformation
0x180013b35  test    eax, eax
0x180013b37  jnz     loc_180013BD2
0x180013b3d  mov     [rsp+250h+var_230], 0
0x180013b45  lea     rdx, [rsp+250h+var_230]; int *
0x180013b4a  lea     rcx, [rsp+250h+var_1E0]; struct _TIME_DYNAMIC_ZONE_INFORMATION *
0x180013b4f  call    ?GetEffectiveOffset@@YAJAEBU_TIME_DYNAMIC_ZONE_INFORMATION@@PEAH@Z; GetEffectiveOffset(_TIME_DYNAMIC_ZONE_INFORMATION const &,int *)
0x180013b54  test    eax, eax
0x180013b56  js      short loc_180013BB6
0x180013b58  mov     ebx, [rsp+250h+var_230]
0x180013b5c  mov     r14d, [rsp+250h+var_1E0.Bias]
0x180013b61  add     r14d, ebx
0x180013b64  lea     rcx, [r15+60h]
0x180013b68  call    ?GetValue@?$ValueProxy@H@Cache@@QEBAAEBHXZ; Cache::ValueProxy<int>::GetValue(void)
0x180013b6d  cmp     [rax], ebx
0x180013b6f  jnz     short loc_180013BB6
0x180013b71  lea     rcx, [r15+70h]
0x180013b75  mov     rax, [rcx]
0x180013b78  cmp     byte ptr [rax+4], 0
0x180013b7c  jz      short loc_180013B88
0x180013b7e  call    ?GetValue@?$ValueProxy@H@Cache@@QEBAAEBHXZ; Cache::ValueProxy<int>::GetValue(void)
0x180013b83  cmp     [rax], r14d
0x180013b86  jnz     short loc_180013BB6
0x180013b88  lea     rdx, [rbp+150h+var_1E0.TimeZoneKeyName]
0x180013b8c  lea     rcx, [rsp+250h+var_208]
0x180013b91  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180013b96  nop
0x180013b97  lea     rdx, [rsp+250h+var_208]
0x180013b9c  lea     rcx, [rsp+250h+var_228]
0x180013ba1  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x180013ba6  nop
0x180013ba7  xor     r8d, r8d
0x180013baa  mov     dl, 1
0x180013bac  lea     rcx, [rsp+250h+var_208]
0x180013bb1  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013bb6  inc     edi
0x180013bb8  lea     rdx, [rsp+250h+var_1E0]
0x180013bbd  mov     ecx, edi
0x180013bbf  call    cs:__imp_EnumDynamicTimeZoneInformation
0x180013bc5  test    eax, eax
0x180013bc7  jz      loc_180013B3D
0x180013bcd  mov     r14, [rsp+250h+var_218]
0x180013bd2  mov     rdi, qword ptr [rsp+250h+var_228+8]
0x180013bd7  mov     rbx, qword ptr [rsp+250h+var_228]
0x180013bdc  mov     r8, rdi
0x180013bdf  sub     r8, rbx
0x180013be2  sar     r8, 5
0x180013be6  mov     rdx, rdi
0x180013be9  mov     rcx, rbx
0x180013bec  call    ??$_Sort@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_J@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0_J@Z; std::_Sort<std::wstring *,__int64>(std::wstring *,std::wstring *,__int64)
0x180013bf1  mov     [rsi], rbx
0x180013bf4  mov     [rsi+8], rdi
0x180013bf8  mov     [rsi+10h], r14
0x180013bfc  xorps   xmm0, xmm0
0x180013bff  movdqu  [rsp+250h+var_228], xmm0
0x180013c05  mov     [rsp+250h+var_218], 0
0x180013c0e  lea     rcx, [rsp+250h+var_228]
0x180013c13  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180013c18  mov     rax, rsi
0x180013c1b  mov     rcx, [rbp+150h+var_30]
0x180013c22  xor     rcx, rsp; StackCookie
0x180013c25  call    __security_check_cookie
0x180013c2a  lea     r11, [rsp+250h+var_20]
0x180013c32  mov     rbx, [r11+30h]
0x180013c36  mov     rsi, [r11+40h]
0x180013c3a  mov     rsp, r11
0x180013c3d  pop     r15
0x180013c3f  pop     r14
0x180013c41  pop     r12
0x180013c43  pop     rdi
0x180013c44  pop     rbp
0x180013c45  retn
```
