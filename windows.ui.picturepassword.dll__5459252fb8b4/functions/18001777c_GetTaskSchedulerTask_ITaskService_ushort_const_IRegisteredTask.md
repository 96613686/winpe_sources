# GetTaskSchedulerTask(ITaskService *,ushort const *,IRegisteredTask * *)

- ea: `0x18001777c`
- end: `0x18001786b`
- name: `?GetTaskSchedulerTask@@YAJPEAUITaskService@@PEBGPEAPEAUIRegisteredTask@@@Z`
- size: `239`
- prototype: `__int64 __fastcall(struct ITaskService *, const unsigned __int16 *, struct IRegisteredTask **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180017bf8`

## callees

- `0x18000934c`
- `0x1800175b8`
- `0x1800175dc`
- `0x18001777c`
- `0x18001f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800177a4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800177a4`

## string_xrefs

- `0x1800177bc`: `shell\lib\comtaskserverutil.cpp`
- `0x180017804`: `shell\lib\comtaskserverutil.cpp`
- `0x18001779a`: `\Microsoft\Windows\Shell\CreateObjectTask`

## pseudocode

```c
__int64 __fastcall GetTaskSchedulerTask(
        struct ITaskService *a1,
        const unsigned __int16 *a2,
        struct IRegisteredTask **a3)
{
  BSTR v5; // rbx
  unsigned int v6; // edi
  struct ITaskServiceVtbl *lpVtbl; // rax
  int v8; // eax
  __int64 v9; // rdx
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  const unsigned __int16 *v13; // [rsp+38h] [rbp+10h] BYREF
  BSTR v14; // [rsp+40h] [rbp+18h] BYREF

  v13 = a2;
  *a3 = 0;
  v14 = SysAllocString(L"\\Microsoft\\Windows\\Shell\\CreateObjectTask");
  v5 = v14;
  if ( v14 )
  {
    lpVtbl = a1->lpVtbl;
    v13 = 0;
    v8 = ((__int64 (__fastcall *)(struct ITaskService *, _QWORD, const unsigned __int16 **))lpVtbl->GetFolder)(
           a1,
           0,
           &v13);
    v6 = v8;
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(const unsigned __int16 *, BSTR, struct IRegisteredTask **))(*(_QWORD *)v13 + 104LL))(
             v13,
             v5,
             a3);
      v6 = v8;
      if ( v8 >= 0 )
      {
        wil::com_ptr_t<ICreateObject,wil::err_returncode_policy>::~com_ptr_t<ICreateObject,wil::err_returncode_policy>((__int64 *)&v13);
        v6 = 0;
        goto LABEL_9;
      }
      v9 = 47;
    }
    else
    {
      v9 = 46;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"shell\\lib\\comtaskserverutil.cpp",
      (const char *)(unsigned int)v8,
      v11);
    wil::com_ptr_t<ICreateObject,wil::err_returncode_policy>::~com_ptr_t<ICreateObject,wil::err_returncode_policy>((__int64 *)&v13);
  }
  else
  {
    v6 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"shell\\lib\\comtaskserverutil.cpp",
      (const char *)0x8007000ELL,
      v11);
  }
LABEL_9:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
  return v6;
}

```

## disassembly

```asm
0x18001777c  mov     [rsp+arg_0], rbx
0x180017781  mov     [rsp+arg_18], rsi
0x180017786  mov     [rsp+arg_8], rdx
0x18001778b  push    rdi; int
0x18001778c  sub     rsp, 20h
0x180017790  mov     rdi, rcx
0x180017793  mov     qword ptr [r8], 0
0x18001779a  lea     rcx, psz; "\\Microsoft\\Windows\\Shell\\CreateObje"...
0x1800177a1  mov     rsi, r8
0x1800177a4  call    cs:__imp_SysAllocString
0x1800177aa  mov     [rsp+28h+arg_10], rax
0x1800177af  mov     rbx, rax
0x1800177b2  test    rax, rax
0x1800177b5  jnz     short loc_1800177D5
0x1800177b7  mov     rcx, [rsp+28h]; this
0x1800177bc  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x1800177c3  mov     edi, 8007000Eh
0x1800177c8  lea     edx, [rax+2Bh]; void *
0x1800177cb  mov     r9d, edi; char *
0x1800177ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800177d3  jmp     short loc_18001784F
0x1800177d5  mov     rax, [rdi]
0x1800177d8  lea     r8, [rsp+28h+arg_8]
0x1800177dd  xor     edx, edx
0x1800177df  mov     [rsp+28h+arg_8], 0
0x1800177e8  mov     rcx, rdi
0x1800177eb  mov     rax, [rax+38h]
0x1800177ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177f4  mov     edi, eax
0x1800177f6  test    eax, eax
0x1800177f8  jns     short loc_18001781F
0x1800177fa  mov     edx, 2Eh ; '.'; void *
0x1800177ff  mov     rcx, [rsp+28h]; this
0x180017804  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x18001780b  mov     r9d, eax; char *
0x18001780e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017813  lea     rcx, [rsp+28h+arg_8]
0x180017818  call    ??1?$com_ptr_t@UICreateObject@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICreateObject,wil::err_returncode_policy>::~com_ptr_t<ICreateObject,wil::err_returncode_policy>(void)
0x18001781d  jmp     short loc_18001784F
0x18001781f  mov     rcx, [rsp+28h+arg_8]
0x180017824  mov     r8, rsi
0x180017827  mov     rdx, rbx
0x18001782a  mov     rax, [rcx]
0x18001782d  mov     rax, [rax+68h]
0x180017831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017836  mov     edi, eax
0x180017838  test    eax, eax
0x18001783a  jns     short loc_180017843
0x18001783c  mov     edx, 2Fh ; '/'
0x180017841  jmp     short loc_1800177FF
0x180017843  lea     rcx, [rsp+28h+arg_8]
0x180017848  call    ??1?$com_ptr_t@UICreateObject@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICreateObject,wil::err_returncode_policy>::~com_ptr_t<ICreateObject,wil::err_returncode_policy>(void)
0x18001784d  xor     edi, edi
0x18001784f  lea     rcx, [rsp+28h+arg_10]
0x180017854  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017859  mov     rbx, [rsp+28h+arg_0]
0x18001785e  mov     eax, edi
0x180017860  mov     rsi, [rsp+28h+arg_18]
0x180017865  add     rsp, 20h
0x180017869  pop     rdi
0x18001786a  retn
```
