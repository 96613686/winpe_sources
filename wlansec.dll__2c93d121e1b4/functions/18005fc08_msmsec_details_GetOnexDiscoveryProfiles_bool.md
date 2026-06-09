# msmsec::details::GetOnexDiscoveryProfiles(bool)

- ea: `0x18005fc08`
- end: `0x18005fd9a`
- name: `?GetOnexDiscoveryProfiles@details@msmsec@@YA?AV?$vector@UOnexProfileFragment@details@msmsec@@V?$allocator@UOnexProfileFragment@details@msmsec@@@std@@@std@@_N@Z`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18005f054`

## callees

- `0x18001fad8`
- `0x180041374`
- `0x18005dd2c`
- `0x18005df04`
- `0x18005e824`
- `0x18005e928`
- `0x18005fc08`

## import_xrefs

- `OneX!OneXCreateDiscoveryProfiles` at `0x18005fca1`
- `OneX!OneXCreateDiscoveryProfiles` at `0x18005fca1`
- `OneX!OneXFreeMemory` at `0x18005fd63`
- `OneX!OneXFreeMemory` at `0x18005fd63`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall msmsec::details::GetOnexDiscoveryProfiles(_QWORD *a1, unsigned __int8 a2)
{
  unsigned int v3; // eax
  __int64 v4; // rcx
  unsigned int v5; // edx
  __int64 v6; // rbx
  __int64 i; // rbx
  __int64 v9; // [rsp+48h] [rbp-11h] BYREF
  __int64 *v10; // [rsp+50h] [rbp-9h] BYREF
  unsigned int v11[2]; // [rsp+58h] [rbp-1h] BYREF
  char v12; // [rsp+60h] [rbp+7h]
  _QWORD v13[2]; // [rsp+68h] [rbp+Fh] BYREF
  char v14; // [rsp+78h] [rbp+1Fh]
  unsigned int *v15; // [rsp+80h] [rbp+27h]
  __int64 *v16; // [rsp+88h] [rbp+2Fh]
  char v17; // [rsp+90h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  unsigned int v19; // [rsp+C8h] [rbp+6Fh] BYREF
  __int64 v20; // [rsp+D0h] [rbp+77h] BYREF
  __int64 v21; // [rsp+D8h] [rbp+7Fh] BYREF

  v19 = 0;
  v21 = 0;
  v20 = 0;
  v15 = &v19;
  v16 = &v20;
  v17 = 1;
  v13[0] = &v20;
  v13[1] = 0;
  v14 = 1;
  v10 = &v21;
  *(_QWORD *)v11 = 0;
  v12 = 1;
  v3 = OneXCreateDiscoveryProfiles(1, 0, a2, &v19);
  if ( v3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x33C,
      (unsigned int)"onecoreuap\\net\\wlan\\msmsec\\src\\capability.cpp",
      (const char *)v3,
      (unsigned int)v11);
  wil::details::out_param_t<std::unique_ptr<unsigned long [0],std::integral_constant<unsigned long (*)(void *),&unsigned long OneXFreeMemory(void *)>>>::~out_param_t<std::unique_ptr<unsigned long [0],std::integral_constant<unsigned long (*)(void *),&unsigned long OneXFreeMemory(void *)>>>(&v10);
  wil::details::out_param_t<std::unique_ptr<unsigned long [0],std::integral_constant<unsigned long (*)(void *),&unsigned long OneXFreeMemory(void *)>>>::~out_param_t<std::unique_ptr<unsigned long [0],std::integral_constant<unsigned long (*)(void *),&unsigned long OneXFreeMemory(void *)>>>(v13);
  std::vector<DOT11_AUTH_CIPHER_PAIR>::vector<DOT11_AUTH_CIPHER_PAIR>(a1);
  v5 = v19;
  v9 = v19;
  if ( v19 > (unsigned __int64)((__int64)(a1[2] - *a1) >> 4) )
  {
    std::vector<msmsec::details::OnexProfileFragment>::_Reallocate<0>(v4, &v9);
    v5 = v19;
  }
  v6 = 0;
  if ( v5 )
  {
    do
    {
      v9 = *(_QWORD *)(v20 + 8 * v6);
      *(_QWORD *)(v20 + 8 * v6) = 0;
      std::vector<msmsec::details::OnexProfileFragment>::emplace_back<unsigned long &,std::unique_ptr<unsigned char [0],std::integral_constant<unsigned long (*)(void *),&unsigned long OneXFreeMemory(void *)>>>(
        a1,
        v21 + 4 * v6,
        &v9);
      std::unique_ptr<unsigned char * [0],std::integral_constant<unsigned long (*)(void *),&unsigned long OneXFreeMemory(void *)>>::~unique_ptr<unsigned char * [0],std::integral_constant<unsigned long (*)(void *),&unsigned long OneXFreeMemory(void *)>>(&v9);
      v6 = (unsigned int)(v6 + 1);
      v5 = v19;
    }
    while ( (unsigned int)v6 < v19 );
  }
  for ( i = 0; (unsigned int)i < v5; i = (unsigned int)(i + 1) )
  {
    if ( *(_QWORD *)(v20 + 8 * i) )
    {
      OneXFreeMemory();
      v5 = v19;
    }
  }
  std::unique_ptr<unsigned char * [0],std::integral_constant<unsigned long (*)(void *),&unsigned long OneXFreeMemory(void *)>>::~unique_ptr<unsigned char * [0],std::integral_constant<unsigned long (*)(void *),&unsigned long OneXFreeMemory(void *)>>(&v20);
  std::unique_ptr<unsigned char * [0],std::integral_constant<unsigned long (*)(void *),&unsigned long OneXFreeMemory(void *)>>::~unique_ptr<unsigned char * [0],std::integral_constant<unsigned long (*)(void *),&unsigned long OneXFreeMemory(void *)>>(&v21);
  return a1;
}

```

## disassembly

```asm
0x18005fc08  mov     [rsp-8+arg_0], rcx
0x18005fc0d  push    rbp
0x18005fc0e  push    rbx
0x18005fc0f  push    rdi
0x18005fc10  lea     rbp, [rsp-47h]
0x18005fc15  sub     rsp, 0A0h
0x18005fc1c  mov     rdi, rcx
0x18005fc1f  mov     [rbp+57h+var_70], 0
0x18005fc26  mov     [rbp+57h+arg_8], 0
0x18005fc2d  mov     [rbp+57h+arg_18], 0
0x18005fc35  mov     [rbp+57h+arg_10], 0
0x18005fc3d  lea     rax, [rbp+57h+arg_8]
0x18005fc41  mov     [rbp+57h+var_30], rax
0x18005fc45  lea     rax, [rbp+57h+arg_10]
0x18005fc49  mov     [rbp+57h+var_28], rax
0x18005fc4d  mov     [rbp+57h+var_20], 1
0x18005fc51  lea     rax, [rbp+57h+arg_10]
0x18005fc55  mov     [rbp+57h+var_48], rax
0x18005fc59  mov     [rbp+57h+var_40], 0
0x18005fc61  mov     [rbp+57h+var_38], 1
0x18005fc65  lea     rax, [rbp+57h+arg_18]
0x18005fc69  mov     [rbp+57h+var_60], rax
0x18005fc6d  mov     qword ptr [rbp+57h+var_58], 0
0x18005fc75  mov     [rbp+57h+var_50], 1
0x18005fc79  movzx   r8d, dl
0x18005fc7d  mov     [rsp+0B0h+var_80], 0
0x18005fc86  lea     rax, [rbp+57h+var_40]
0x18005fc8a  mov     [rsp+0B0h+var_88], rax
0x18005fc8f  lea     rax, [rbp+57h+var_58]
0x18005fc93  mov     qword ptr [rsp+0B0h+var_90], rax; unsigned int
0x18005fc98  lea     r9, [rbp+57h+arg_8]
0x18005fc9c  xor     edx, edx
0x18005fc9e  lea     ecx, [rdx+1]
0x18005fca1  call    cs:__imp_OneXCreateDiscoveryProfiles
0x18005fca8  nop     dword ptr [rax+rax+00h]
0x18005fcad  mov     rcx, [rbp+5Fh]; this
0x18005fcb1  test    eax, eax
0x18005fcb3  jz      short loc_18005FCCA
0x18005fcb5  mov     r9d, eax; char *
0x18005fcb8  lea     r8, aOnecoreuapNetW_7; "onecoreuap\\net\\wlan\\msmsec\\src\\cap"...
0x18005fcbf  mov     edx, 33Ch; void *
0x18005fcc4  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18005fcca  lea     rcx, [rbp+57h+var_60]
0x18005fcce  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@KU?$integral_constant@P6AKPEAX@Z$1?OneXFreeMemory@@YAK0@Z@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ulong [0],std::integral_constant<ulong (*)(void *),&OneXFreeMemory(void *)>>>::~out_param_t<std::unique_ptr<ulong [0],std::integral_constant<ulong (*)(void *),&OneXFreeMemory(void *)>>>(void)
0x18005fcd3  nop
0x18005fcd4  lea     rcx, [rbp+57h+var_48]
0x18005fcd8  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@KU?$integral_constant@P6AKPEAX@Z$1?OneXFreeMemory@@YAK0@Z@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ulong [0],std::integral_constant<ulong (*)(void *),&OneXFreeMemory(void *)>>>::~out_param_t<std::unique_ptr<ulong [0],std::integral_constant<ulong (*)(void *),&OneXFreeMemory(void *)>>>(void)
0x18005fcdd  mov     rcx, rdi
0x18005fce0  call    ??0?$vector@UDOT11_AUTH_CIPHER_PAIR@@V?$allocator@UDOT11_AUTH_CIPHER_PAIR@@@std@@@std@@QEAA@XZ; std::vector<DOT11_AUTH_CIPHER_PAIR>::vector<DOT11_AUTH_CIPHER_PAIR>(void)
0x18005fce5  mov     [rbp+57h+var_70], 1
0x18005fcec  mov     edx, [rbp+57h+arg_8]
0x18005fcef  mov     [rbp+57h+var_68], rdx
0x18005fcf3  mov     rax, [rdi+10h]
0x18005fcf7  sub     rax, [rdi]
0x18005fcfa  sar     rax, 4
0x18005fcfe  cmp     rdx, rax
0x18005fd01  jbe     short loc_18005FD0F
0x18005fd03  lea     rdx, [rbp+57h+var_68]
0x18005fd07  call    ??$_Reallocate@$0A@@?$vector@UOnexProfileFragment@details@msmsec@@V?$allocator@UOnexProfileFragment@details@msmsec@@@std@@@std@@AEAAXAEA_K@Z; std::vector<msmsec::details::OnexProfileFragment>::_Reallocate<0>(unsigned __int64 &)
0x18005fd0c  mov     edx, [rbp+57h+arg_8]
0x18005fd0f  xor     ebx, ebx
0x18005fd11  test    edx, edx
0x18005fd13  jz      short loc_18005FD50
0x18005fd15  mov     rcx, [rbp+57h+arg_10]
0x18005fd19  mov     rax, [rcx+rbx*8]
0x18005fd1d  mov     [rbp+57h+var_68], rax
0x18005fd21  mov     qword ptr [rcx+rbx*8], 0
0x18005fd29  mov     rax, [rbp+57h+arg_18]
0x18005fd2d  lea     rdx, [rax+rbx*4]
0x18005fd31  lea     r8, [rbp+57h+var_68]
0x18005fd35  mov     rcx, rdi
0x18005fd38  call    ??$emplace_back@AEAKV?$unique_ptr@$$BY0A@EU?$integral_constant@P6AKPEAX@Z$1?OneXFreeMemory@@YAK0@Z@std@@@std@@@?$vector@UOnexProfileFragment@details@msmsec@@V?$allocator@UOnexProfileFragment@details@msmsec@@@std@@@std@@QEAAAEAUOnexProfileFragment@details@msmsec@@AEAK$$QEAV?$unique_ptr@$$BY0A@EU?$integral_constant@P6AKPEAX@Z$1?OneXFreeMemory@@YAK0@Z@std@@@1@@Z; std::vector<msmsec::details::OnexProfileFragment>::emplace_back<ulong &,std::unique_ptr<uchar [0],std::integral_constant<ulong (*)(void *),&OneXFreeMemory(void *)>>>(ulong &,std::unique_ptr<uchar [0],std::integral_constant<ulong (*)(void *),&OneXFreeMemory(void *)>> &&)
0x18005fd3d  nop
0x18005fd3e  lea     rcx, [rbp+57h+var_68]
0x18005fd42  call    ??1?$unique_ptr@$$BY0A@PEAEU?$integral_constant@P6AKPEAX@Z$1?OneXFreeMemory@@YAK0@Z@std@@@std@@QEAA@XZ; std::unique_ptr<uchar * [0],std::integral_constant<ulong (*)(void *),&OneXFreeMemory(void *)>>::~unique_ptr<uchar * [0],std::integral_constant<ulong (*)(void *),&OneXFreeMemory(void *)>>(void)
0x18005fd47  inc     ebx
0x18005fd49  mov     edx, [rbp+57h+arg_8]
0x18005fd4c  cmp     ebx, edx
0x18005fd4e  jb      short loc_18005FD15
0x18005fd50  xor     ebx, ebx
0x18005fd52  test    edx, edx
0x18005fd54  jz      short loc_18005FD78
0x18005fd56  mov     rax, [rbp+57h+arg_10]
0x18005fd5a  mov     rcx, [rax+rbx*8]
0x18005fd5e  test    rcx, rcx
0x18005fd61  jz      short loc_18005FD72
0x18005fd63  call    cs:__imp_OneXFreeMemory
0x18005fd6a  nop     dword ptr [rax+rax+00h]
0x18005fd6f  mov     edx, [rbp+57h+arg_8]
0x18005fd72  inc     ebx
0x18005fd74  cmp     ebx, edx
0x18005fd76  jb      short loc_18005FD56
0x18005fd78  lea     rcx, [rbp+57h+arg_10]
0x18005fd7c  call    ??1?$unique_ptr@$$BY0A@PEAEU?$integral_constant@P6AKPEAX@Z$1?OneXFreeMemory@@YAK0@Z@std@@@std@@QEAA@XZ; std::unique_ptr<uchar * [0],std::integral_constant<ulong (*)(void *),&OneXFreeMemory(void *)>>::~unique_ptr<uchar * [0],std::integral_constant<ulong (*)(void *),&OneXFreeMemory(void *)>>(void)
0x18005fd81  nop
0x18005fd82  lea     rcx, [rbp+57h+arg_18]
0x18005fd86  call    ??1?$unique_ptr@$$BY0A@PEAEU?$integral_constant@P6AKPEAX@Z$1?OneXFreeMemory@@YAK0@Z@std@@@std@@QEAA@XZ; std::unique_ptr<uchar * [0],std::integral_constant<ulong (*)(void *),&OneXFreeMemory(void *)>>::~unique_ptr<uchar * [0],std::integral_constant<ulong (*)(void *),&OneXFreeMemory(void *)>>(void)
0x18005fd8b  mov     rax, rdi
0x18005fd8e  add     rsp, 0A0h
0x18005fd95  pop     rdi
0x18005fd96  pop     rbx
0x18005fd97  pop     rbp
0x18005fd98  retn
```
