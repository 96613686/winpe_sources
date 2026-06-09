# tson::load_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::input_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)

- ea: `0x180007748`
- end: `0x18000791d`
- name: `??$load_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z`
- size: `469`
- prototype: `void __fastcall(tson::input_archive *this, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006924`

## callees

- `0x18000682c`
- `0x180007748`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800077dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800078a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800078f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800077dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800078a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800078f7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007865`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007865`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800077fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800078c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800077fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800078c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800077ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007857`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800078b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800077ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007857`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800078b3`

## pseudocode

```c
void __fastcall tson::load_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        tson::input_archive *this,
        void **a2)
{
  __int64 v4; // rbx
  char *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rax
  unsigned __int16 v8; // cx
  unsigned __int16 *v9; // rdx
  unsigned __int64 v10; // rdi
  void *v11; // rcx
  void *v12; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int64 v14; // rax
  __int64 v15; // rbp
  HANDLE v16; // rax
  _QWORD *v17; // r15
  char v18; // al
  unsigned __int64 v19; // rdi
  _QWORD *v20; // rcx
  void *v21; // rcx
  void *v22; // rdi
  HANDLE v23; // rax
  void *v24; // rcx
  void *v25; // [rsp+20h] [rbp-38h] BYREF

  v4 = 0;
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
    v8 = 0;
    v9 = *(unsigned __int16 **)(*(_QWORD *)this + 8LL);
    if ( (unsigned __int64)(v9 + 1) > *(_QWORD *)(*(_QWORD *)this + 16LL) )
    {
      *(_BYTE *)(v7 + 24) = 1;
    }
    else
    {
      v8 = *v9;
      *(_QWORD *)(v7 + 8) = v9 + 1;
    }
    v4 = v8;
  }
  if ( *a2 )
  {
    v10 = 0;
    if ( a2[2] )
    {
      do
      {
        v11 = (void *)*((_QWORD *)*a2 + v10);
        if ( v11 )
          CoTaskMemFree(v11);
        ++v10;
      }
      while ( v10 < (unsigned __int64)a2[2] );
    }
    v12 = *a2;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v12);
    *a2 = 0;
  }
  a2[1] = 0;
  a2[2] = 0;
  while ( v4 )
  {
    v25 = 0;
    --v4;
    tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(
      this,
      &v25);
    v14 = (unsigned __int64)a2[1];
    if ( (unsigned __int64)a2[2] < v14 )
      goto LABEL_36;
    if ( v14 )
    {
      v15 = 2 * v14;
      if ( 2 * v14 <= v14 )
        goto LABEL_33;
    }
    else
    {
      v15 = 10;
    }
    v16 = GetProcessHeap();
    v17 = HeapAlloc(v16, 0, 8 * v15);
    if ( !v17 )
    {
      v18 = 0;
      goto LABEL_34;
    }
    if ( *a2 )
    {
      v19 = 0;
      if ( a2[2] )
      {
        do
        {
          v20 = *a2;
          v17[v19] = *((_QWORD *)*a2 + v19);
          v20[v19] = 0;
          v21 = (void *)*((_QWORD *)*a2 + v19);
          if ( v21 )
            CoTaskMemFree(v21);
          ++v19;
        }
        while ( v19 < (unsigned __int64)a2[2] );
      }
      v22 = *a2;
      v23 = GetProcessHeap();
      HeapFree(v23, 0, v22);
    }
    *a2 = v17;
    a2[1] = (void *)v15;
LABEL_33:
    v18 = 1;
LABEL_34:
    if ( v18 )
    {
LABEL_36:
      *((_QWORD *)*a2 + (_QWORD)a2[2]) = v25;
      v24 = 0;
      a2[2] = (char *)a2[2] + 1;
      goto LABEL_37;
    }
    v24 = v25;
LABEL_37:
    if ( v24 )
      CoTaskMemFree(v24);
  }
}

```

## disassembly

```asm
0x180007748  mov     [rsp+arg_10], rbx
0x18000774d  mov     [rsp+arg_18], rbp
0x180007752  push    rsi
0x180007753  push    rdi
0x180007754  push    r12
0x180007756  push    r14
0x180007758  push    r15
0x18000775a  sub     rsp, 30h
0x18000775e  xor     r12d, r12d
0x180007761  mov     rsi, rdx
0x180007764  mov     r14, rcx
0x180007767  mov     ebx, r12d
0x18000776a  cmp     [rcx+19h], r12b
0x18000776e  jnz     short loc_1800077C3
0x180007770  lea     rax, [rcx+20h]
0x180007774  mov     rcx, [rax+68h]
0x180007778  test    rcx, rcx
0x18000777b  jz      short loc_180007787
0x18000777d  lea     rax, [rax+rcx*4]
0x180007781  add     rax, 0FFFFFFFFFFFFFFFCh
0x180007785  jmp     short loc_18000778A
0x180007787  mov     byte ptr [rax], 1
0x18000778a  cmp     dword ptr [rax+4], 1
0x18000778e  jz      short loc_18000779E
0x180007790  cmp     [r14+8], r12d
0x180007794  jl      short loc_18000779E
0x180007796  mov     dword ptr [r14+8], 8007065Dh
0x18000779e  mov     rax, [r14]
0x1800077a1  movzx   ecx, r12w
0x1800077a5  mov     rdx, [rax+8]
0x1800077a9  lea     r8, [rdx+2]
0x1800077ad  cmp     r8, [rax+10h]
0x1800077b1  ja      short loc_1800077BC
0x1800077b3  movzx   ecx, word ptr [rdx]
0x1800077b6  mov     [rax+8], r8
0x1800077ba  jmp     short loc_1800077C0
0x1800077bc  mov     byte ptr [rax+18h], 1
0x1800077c0  movzx   ebx, cx
0x1800077c3  cmp     [rsi], r12
0x1800077c6  jz      short loc_180007806
0x1800077c8  mov     rdi, r12
0x1800077cb  cmp     [rsi+10h], r12
0x1800077cf  jbe     short loc_1800077EC
0x1800077d1  mov     rax, [rsi]
0x1800077d4  mov     rcx, [rax+rdi*8]; pv
0x1800077d8  test    rcx, rcx
0x1800077db  jz      short loc_1800077E3
0x1800077dd  call    cs:__imp_CoTaskMemFree
0x1800077e3  inc     rdi
0x1800077e6  cmp     rdi, [rsi+10h]
0x1800077ea  jb      short loc_1800077D1
0x1800077ec  mov     rdi, [rsi]
0x1800077ef  call    cs:__imp_GetProcessHeap
0x1800077f5  mov     r8, rdi; lpMem
0x1800077f8  xor     edx, edx; dwFlags
0x1800077fa  mov     rcx, rax; hHeap
0x1800077fd  call    cs:__imp_HeapFree
0x180007803  mov     [rsi], r12
0x180007806  mov     [rsi+8], r12
0x18000780a  mov     [rsi+10h], r12
0x18000780e  jmp     loc_1800078FD
0x180007813  lea     rdx, [rsp+58h+var_38]
0x180007818  mov     [rsp+58h+var_38], r12
0x18000781d  mov     rcx, r14; this
0x180007820  dec     rbx
0x180007823  call    ??$?RAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@QEAAAEAV01@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)
0x180007828  mov     rax, [rsi+8]
0x18000782c  cmp     [rsi+10h], rax
0x180007830  jb      loc_1800078DB
0x180007836  test    rax, rax
0x180007839  jz      short loc_18000784A
0x18000783b  lea     rbp, [rax+rax]
0x18000783f  cmp     rbp, rax
0x180007842  jbe     loc_1800078CE
0x180007848  jmp     short loc_18000784F
0x18000784a  mov     ebp, 0Ah
0x18000784f  lea     rdi, ds:0[rbp*8]
0x180007857  call    cs:__imp_GetProcessHeap
0x18000785d  mov     r8, rdi; dwBytes
0x180007860  xor     edx, edx; dwFlags
0x180007862  mov     rcx, rax; hHeap
0x180007865  call    cs:__imp_HeapAlloc
0x18000786b  mov     r15, rax
0x18000786e  test    rax, rax
0x180007871  jnz     short loc_180007878
0x180007873  mov     al, r12b
0x180007876  jmp     short loc_1800078D0
0x180007878  cmp     [rsi], r12
0x18000787b  jz      short loc_1800078C7
0x18000787d  mov     rdi, r12
0x180007880  cmp     [rsi+10h], r12
0x180007884  jbe     short loc_1800078B0
0x180007886  mov     rcx, [rsi]
0x180007889  mov     rax, [rcx+rdi*8]
0x18000788d  mov     [r15+rdi*8], rax
0x180007891  mov     [rcx+rdi*8], r12
0x180007895  mov     rax, [rsi]
0x180007898  mov     rcx, [rax+rdi*8]; pv
0x18000789c  test    rcx, rcx
0x18000789f  jz      short loc_1800078A7
0x1800078a1  call    cs:__imp_CoTaskMemFree
0x1800078a7  inc     rdi
0x1800078aa  cmp     rdi, [rsi+10h]
0x1800078ae  jb      short loc_180007886
0x1800078b0  mov     rdi, [rsi]
0x1800078b3  call    cs:__imp_GetProcessHeap
0x1800078b9  mov     r8, rdi; lpMem
0x1800078bc  xor     edx, edx; dwFlags
0x1800078be  mov     rcx, rax; hHeap
0x1800078c1  call    cs:__imp_HeapFree
0x1800078c7  mov     [rsi], r15
0x1800078ca  mov     [rsi+8], rbp
0x1800078ce  mov     al, 1
0x1800078d0  test    al, al
0x1800078d2  jnz     short loc_1800078DB
0x1800078d4  mov     rcx, [rsp+58h+var_38]
0x1800078d9  jmp     short loc_1800078F2
0x1800078db  mov     rdx, [rsi+10h]
0x1800078df  mov     rcx, [rsi]
0x1800078e2  mov     rax, [rsp+58h+var_38]
0x1800078e7  mov     [rcx+rdx*8], rax
0x1800078eb  mov     rcx, r12; pv
0x1800078ee  inc     qword ptr [rsi+10h]
0x1800078f2  test    rcx, rcx
0x1800078f5  jz      short loc_1800078FD
0x1800078f7  call    cs:__imp_CoTaskMemFree
0x1800078fd  test    rbx, rbx
0x180007900  jnz     loc_180007813
0x180007906  mov     rbx, [rsp+58h+arg_10]
0x18000790b  mov     rbp, [rsp+58h+arg_18]
0x180007910  add     rsp, 30h
0x180007914  pop     r15
0x180007916  pop     r14
0x180007918  pop     r12
0x18000791a  pop     rdi
0x18000791b  pop     rsi
0x18000791c  retn
```
