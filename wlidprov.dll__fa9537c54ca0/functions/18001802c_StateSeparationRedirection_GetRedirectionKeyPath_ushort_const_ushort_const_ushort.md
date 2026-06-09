# StateSeparationRedirection::GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)

- ea: `0x18001802c`
- end: `0x18001815e`
- name: `?GetRedirectionKeyPath@StateSeparationRedirection@@YAJPEBG0PEAPEAG@Z`
- size: `306`
- prototype: `__int64 __fastcall(StateSeparationRedirection *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003d980`
- `0x18003dae0`

## callees

- `0x180016758`
- `0x18001802c`
- `0x180028650`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800180c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800180c4`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180018072`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180018100`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180018072`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180018100`

## pseudocode

```c
__int64 __fastcall StateSeparationRedirection::GetRedirectionKeyPath(
        StateSeparationRedirection *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  int PersistedRegistryLocationW; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  StateSeparationRedirection *v9; // rax
  StateSeparationRedirection *v10; // rbx
  unsigned int v11; // edi
  __int64 v12; // rdx
  int v13; // eax
  unsigned int *p_cb; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  StateSeparationRedirection *v16; // [rsp+40h] [rbp+8h] BYREF
  unsigned int cb; // [rsp+48h] [rbp+10h] BYREF
  int cb_4; // [rsp+4Ch] [rbp+14h]

  cb_4 = HIDWORD(a2);
  v16 = this;
  cb = 0;
  *(_QWORD *)a3 = 0;
  p_cb = &cb;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(L"IdentityCRL", L"Software\\Microsoft\\IdentityCRL", 0, 0);
  v6 = PersistedRegistryLocationW;
  if ( !PersistedRegistryLocationW )
  {
    v6 = -2147418113;
    v7 = 31;
    goto LABEL_3;
  }
  if ( PersistedRegistryLocationW != 234 )
  {
    if ( PersistedRegistryLocationW > 0 )
      v6 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
    if ( (v6 & 0x80000000) == 0 )
      return v6;
    v7 = 32;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\lib\\stateseparationredirection\\stateseparationredirection.cpp",
      (const char *)v6,
      (int)&cb);
    return v6;
  }
  v9 = (StateSeparationRedirection *)CoTaskMemAlloc(cb);
  v16 = v9;
  v10 = v9;
  if ( v9 )
  {
    LODWORD(p_cb) = 0;
    v13 = GetPersistedRegistryLocationW(L"IdentityCRL", L"Software\\Microsoft\\IdentityCRL", v9, cb);
    v11 = v13;
    if ( v13 > 0 )
      v11 = (unsigned __int16)v13 | 0x80070000;
    if ( (v11 & 0x80000000) == 0 )
    {
      v16 = 0;
      v11 = 0;
      *(_QWORD *)a3 = v10;
      goto LABEL_18;
    }
    v12 = 46;
  }
  else
  {
    v11 = -2147024882;
    v12 = 37;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\lib\\stateseparationredirection\\stateseparationredirection.cpp",
    (const char *)v11,
    (int)p_cb);
LABEL_18:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v16);
  return v11;
}

```

## disassembly

```asm
0x18001802c  mov     rax, rsp
0x18001802f  mov     [rax+18h], rbx
0x180018033  mov     [rax+20h], rsi
0x180018037  mov     [rax+10h], rdx
0x18001803b  mov     [rax+8], rcx
0x18001803f  push    rdi
0x180018040  sub     rsp, 30h
0x180018044  mov     dword ptr [rax+10h], 0
0x18001804b  lea     rax, [rax+10h]
0x18001804f  mov     rsi, r8
0x180018052  mov     qword ptr [r8], 0
0x180018059  xor     r9d, r9d
0x18001805c  mov     qword ptr [rsp+38h+var_18], rax; int
0x180018061  xor     r8d, r8d
0x180018064  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\IdentityCRL"
0x18001806b  lea     rcx, aIdentitycrl; "IdentityCRL"
0x180018072  call    cs:__imp_GetPersistedRegistryLocationW
0x180018078  mov     ebx, eax
0x18001807a  test    eax, eax
0x18001807c  jnz     short loc_1800180A1
0x18001807e  mov     ebx, 8000FFFFh
0x180018083  lea     edx, [rax+1Fh]; void *
0x180018086  mov     rcx, [rsp+38h]; this
0x18001808b  lea     r8, aOnecoreuapDsEx_9; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180018092  mov     r9d, ebx; char *
0x180018095  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001809a  mov     eax, ebx
0x18001809c  jmp     loc_18001814E
0x1800180a1  cmp     eax, 0EAh
0x1800180a6  jz      short loc_1800180C0
0x1800180a8  test    eax, eax
0x1800180aa  jle     short loc_1800180B5
0x1800180ac  movzx   ebx, ax
0x1800180af  or      ebx, 80070000h
0x1800180b5  test    ebx, ebx
0x1800180b7  jns     short loc_18001809A
0x1800180b9  mov     edx, 20h ; ' '
0x1800180be  jmp     short loc_180018086
0x1800180c0  mov     ecx, dword ptr [rsp+38h+cb]; cb
0x1800180c4  call    cs:__imp_CoTaskMemAlloc
0x1800180ca  mov     [rsp+38h+arg_0], rax
0x1800180cf  mov     rbx, rax
0x1800180d2  test    rax, rax
0x1800180d5  jnz     short loc_1800180E1
0x1800180d7  mov     edi, 8007000Eh
0x1800180dc  lea     edx, [rax+25h]
0x1800180df  jmp     short loc_18001811E
0x1800180e1  mov     r9d, dword ptr [rsp+38h+cb]
0x1800180e6  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\IdentityCRL"
0x1800180ed  mov     r8, rbx
0x1800180f0  mov     qword ptr [rsp+38h+var_18], 0; int
0x1800180f9  lea     rcx, aIdentitycrl; "IdentityCRL"
0x180018100  call    cs:__imp_GetPersistedRegistryLocationW
0x180018106  mov     edi, eax
0x180018108  test    eax, eax
0x18001810a  jle     short loc_180018115
0x18001810c  movzx   edi, ax
0x18001810f  or      edi, 80070000h
0x180018115  test    edi, edi
0x180018117  jns     short loc_180018134
0x180018119  mov     edx, 2Eh ; '.'; void *
0x18001811e  mov     rcx, [rsp+38h]; this
0x180018123  lea     r8, aOnecoreuapDsEx_9; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001812a  mov     r9d, edi; char *
0x18001812d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018132  jmp     short loc_180018142
0x180018134  mov     [rsp+38h+arg_0], 0
0x18001813d  xor     edi, edi
0x18001813f  mov     [rsi], rbx
0x180018142  lea     rcx, [rsp+38h+arg_0]
0x180018147  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001814c  mov     eax, edi
0x18001814e  mov     rbx, [rsp+38h+arg_10]
0x180018153  mov     rsi, [rsp+38h+arg_18]
0x180018158  add     rsp, 30h
0x18001815c  pop     rdi
0x18001815d  retn
```
