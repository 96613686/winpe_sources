# tson::load_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::input_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)

- ea: `0x18000e980`
- end: `0x18000eb49`
- name: `??$load_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z`
- size: `457`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000de78`

## callees

- `0x18000dc28`
- `0x18000e980`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ea17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ea8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eaea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ea17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ea8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eaea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ea25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eaf8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ea25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eaf8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ea9d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ea9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ea05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ead8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000eb2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ea05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ead8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000eb2d`

## pseudocode

```c
void __fastcall tson::load_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        tson::input_archive *this,
        void **a2)
{
  __int64 v2; // rbx
  char *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rax
  unsigned __int16 *v8; // rcx
  _WORD *v9; // rdx
  unsigned __int16 v10; // cx
  unsigned __int64 v11; // rdi
  void *v12; // rcx
  void *v13; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int64 v15; // rax
  __int64 v16; // rbp
  HANDLE v17; // rax
  _QWORD *v18; // rax
  _QWORD *v19; // r15
  unsigned __int64 v20; // rdi
  _QWORD *v21; // rcx
  void *v22; // rcx
  void *v23; // rdi
  HANDLE v24; // rax
  void *v25; // rcx
  void *v26; // [rsp+60h] [rbp+8h] BYREF

  v2 = 0;
  if ( !*((_BYTE *)this + 25) )
  {
    v5 = (char *)this + 32;
    v6 = *((_QWORD *)this + 17);
    if ( v6 )
      v5 = &v5[4 * v6 - 4];
    else
      *v5 = 1;
    if ( *((_DWORD *)v5 + 1) != 1 && *((int *)this + 2) >= 0 )
      *((_DWORD *)this + 2) = -2147023267;
    v7 = *(_QWORD *)this;
    v8 = *(unsigned __int16 **)(*(_QWORD *)this + 8LL);
    v9 = v8 + 1;
    if ( (unsigned __int64)(v8 + 1) > *(_QWORD *)(*(_QWORD *)this + 16LL) )
    {
      v10 = 0;
      *(_BYTE *)(v7 + 24) = 1;
    }
    else
    {
      v10 = *v8;
      *(_QWORD *)(v7 + 8) = v9;
    }
    v2 = v10;
  }
  if ( *a2 )
  {
    v11 = 0;
    if ( a2[2] )
    {
      do
      {
        v12 = (void *)*((_QWORD *)*a2 + v11);
        if ( v12 )
          CoTaskMemFree(v12);
        ++v11;
      }
      while ( v11 < (unsigned __int64)a2[2] );
    }
    v13 = *a2;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v13);
    *a2 = 0;
  }
  a2[1] = 0;
  a2[2] = 0;
  while ( v2 )
  {
    v26 = 0;
    --v2;
    tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(
      this,
      &v26);
    v15 = (unsigned __int64)a2[1];
    if ( (unsigned __int64)a2[2] < v15 )
      goto LABEL_35;
    if ( v15 )
    {
      v16 = 2 * v15;
      if ( 2 * v15 <= v15 )
        goto LABEL_32;
    }
    else
    {
      v16 = 10;
    }
    v17 = GetProcessHeap();
    v18 = HeapAlloc(v17, 0, 8 * v16);
    v19 = v18;
    if ( !v18 )
      goto LABEL_33;
    if ( *a2 )
    {
      v20 = 0;
      if ( a2[2] )
      {
        do
        {
          v21 = *a2;
          v19[v20] = *((_QWORD *)*a2 + v20);
          v21[v20] = 0;
          v22 = (void *)*((_QWORD *)*a2 + v20);
          if ( v22 )
            CoTaskMemFree(v22);
          ++v20;
        }
        while ( v20 < (unsigned __int64)a2[2] );
      }
      v23 = *a2;
      v24 = GetProcessHeap();
      HeapFree(v24, 0, v23);
    }
    *a2 = v19;
    a2[1] = (void *)v16;
LABEL_32:
    LOBYTE(v18) = 1;
LABEL_33:
    if ( (_BYTE)v18 )
    {
LABEL_35:
      *((_QWORD *)*a2 + (_QWORD)a2[2]) = v26;
      v25 = 0;
      a2[2] = (char *)a2[2] + 1;
      goto LABEL_36;
    }
    v25 = v26;
LABEL_36:
    if ( v25 )
      CoTaskMemFree(v25);
  }
}

```

## disassembly

```asm
0x18000e980  push    rbx
0x18000e982  push    rbp
0x18000e983  push    rsi
0x18000e984  push    rdi
0x18000e985  push    r14
0x18000e987  push    r15
0x18000e989  sub     rsp, 28h
0x18000e98d  xor     ebx, ebx
0x18000e98f  mov     rsi, rdx
0x18000e992  mov     r14, rcx
0x18000e995  cmp     [rcx+19h], bl
0x18000e998  jnz     short loc_18000E9EB
0x18000e99a  lea     rax, [rcx+20h]
0x18000e99e  mov     rcx, [rax+68h]
0x18000e9a2  test    rcx, rcx
0x18000e9a5  jz      short loc_18000E9B1
0x18000e9a7  lea     rax, [rax+rcx*4]
0x18000e9ab  add     rax, 0FFFFFFFFFFFFFFFCh
0x18000e9af  jmp     short loc_18000E9B4
0x18000e9b1  mov     byte ptr [rax], 1
0x18000e9b4  cmp     dword ptr [rax+4], 1
0x18000e9b8  jz      short loc_18000E9C8
0x18000e9ba  cmp     [r14+8], ebx
0x18000e9be  jl      short loc_18000E9C8
0x18000e9c0  mov     dword ptr [r14+8], 8007065Dh
0x18000e9c8  mov     rax, [r14]
0x18000e9cb  mov     rcx, [rax+8]
0x18000e9cf  lea     rdx, [rcx+2]
0x18000e9d3  cmp     rdx, [rax+10h]
0x18000e9d7  ja      short loc_18000E9E2
0x18000e9d9  movzx   ecx, word ptr [rcx]
0x18000e9dc  mov     [rax+8], rdx
0x18000e9e0  jmp     short loc_18000E9E8
0x18000e9e2  xor     ecx, ecx
0x18000e9e4  mov     byte ptr [rax+18h], 1
0x18000e9e8  movzx   ebx, cx
0x18000e9eb  cmp     qword ptr [rsi], 0
0x18000e9ef  jz      short loc_18000EA32
0x18000e9f1  xor     edi, edi
0x18000e9f3  cmp     [rsi+10h], rdi
0x18000e9f7  jbe     short loc_18000EA14
0x18000e9f9  mov     rax, [rsi]
0x18000e9fc  mov     rcx, [rax+rdi*8]; pv
0x18000ea00  test    rcx, rcx
0x18000ea03  jz      short loc_18000EA0B
0x18000ea05  call    cs:__imp_CoTaskMemFree
0x18000ea0b  inc     rdi
0x18000ea0e  cmp     rdi, [rsi+10h]
0x18000ea12  jb      short loc_18000E9F9
0x18000ea14  mov     rdi, [rsi]
0x18000ea17  call    cs:__imp_GetProcessHeap
0x18000ea1d  mov     r8, rdi; lpMem
0x18000ea20  xor     edx, edx; dwFlags
0x18000ea22  mov     rcx, rax; hHeap
0x18000ea25  call    cs:__imp_HeapFree
0x18000ea2b  mov     qword ptr [rsi], 0
0x18000ea32  mov     qword ptr [rsi+8], 0
0x18000ea3a  mov     qword ptr [rsi+10h], 0
0x18000ea42  jmp     loc_18000EB33
0x18000ea47  lea     rdx, [rsp+58h+arg_0]
0x18000ea4c  mov     [rsp+58h+arg_0], 0
0x18000ea55  mov     rcx, r14; this
0x18000ea58  dec     rbx
0x18000ea5b  call    ??$?RAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@QEAAAEAV01@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)
0x18000ea60  mov     rax, [rsi+8]
0x18000ea64  cmp     [rsi+10h], rax
0x18000ea68  jb      loc_18000EB12
0x18000ea6e  test    rax, rax
0x18000ea71  jz      short loc_18000EA82
0x18000ea73  lea     rbp, [rax+rax]
0x18000ea77  cmp     rbp, rax
0x18000ea7a  jbe     loc_18000EB05
0x18000ea80  jmp     short loc_18000EA87
0x18000ea82  mov     ebp, 0Ah
0x18000ea87  lea     rdi, ds:0[rbp*8]
0x18000ea8f  call    cs:__imp_GetProcessHeap
0x18000ea95  mov     r8, rdi; dwBytes
0x18000ea98  xor     edx, edx; dwFlags
0x18000ea9a  mov     rcx, rax; hHeap
0x18000ea9d  call    cs:__imp_HeapAlloc
0x18000eaa3  mov     r15, rax
0x18000eaa6  test    rax, rax
0x18000eaa9  jz      short loc_18000EB07
0x18000eaab  cmp     qword ptr [rsi], 0
0x18000eaaf  jz      short loc_18000EAFE
0x18000eab1  xor     edi, edi
0x18000eab3  cmp     [rsi+10h], rdi
0x18000eab7  jbe     short loc_18000EAE7
0x18000eab9  mov     rcx, [rsi]
0x18000eabc  mov     rax, [rcx+rdi*8]
0x18000eac0  mov     [r15+rdi*8], rax
0x18000eac4  mov     qword ptr [rcx+rdi*8], 0
0x18000eacc  mov     rax, [rsi]
0x18000eacf  mov     rcx, [rax+rdi*8]; pv
0x18000ead3  test    rcx, rcx
0x18000ead6  jz      short loc_18000EADE
0x18000ead8  call    cs:__imp_CoTaskMemFree
0x18000eade  inc     rdi
0x18000eae1  cmp     rdi, [rsi+10h]
0x18000eae5  jb      short loc_18000EAB9
0x18000eae7  mov     rdi, [rsi]
0x18000eaea  call    cs:__imp_GetProcessHeap
0x18000eaf0  mov     r8, rdi; lpMem
0x18000eaf3  xor     edx, edx; dwFlags
0x18000eaf5  mov     rcx, rax; hHeap
0x18000eaf8  call    cs:__imp_HeapFree
0x18000eafe  mov     [rsi], r15
0x18000eb01  mov     [rsi+8], rbp
0x18000eb05  mov     al, 1
0x18000eb07  test    al, al
0x18000eb09  jnz     short loc_18000EB12
0x18000eb0b  mov     rcx, [rsp+58h+arg_0]
0x18000eb10  jmp     short loc_18000EB28
0x18000eb12  mov     rdx, [rsi+10h]
0x18000eb16  mov     rcx, [rsi]
0x18000eb19  mov     rax, [rsp+58h+arg_0]
0x18000eb1e  mov     [rcx+rdx*8], rax
0x18000eb22  xor     ecx, ecx; pv
0x18000eb24  inc     qword ptr [rsi+10h]
0x18000eb28  test    rcx, rcx
0x18000eb2b  jz      short loc_18000EB33
0x18000eb2d  call    cs:__imp_CoTaskMemFree
0x18000eb33  test    rbx, rbx
0x18000eb36  jnz     loc_18000EA47
0x18000eb3c  add     rsp, 28h
0x18000eb40  pop     r15
0x18000eb42  pop     r14
0x18000eb44  pop     rdi
0x18000eb45  pop     rsi
0x18000eb46  pop     rbp
0x18000eb47  pop     rbx
0x18000eb48  retn
```
