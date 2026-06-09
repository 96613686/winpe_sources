# TaskDefinitionImpl::WriteMaintenanceSettings(TaskXmlWriter &,ITaskSettings3 *)

- ea: `0x180001b70`
- end: `0x180001d46`
- name: `?WriteMaintenanceSettings@TaskDefinitionImpl@@AEAAJAEAVTaskXmlWriter@@PEAUITaskSettings3@@@Z`
- size: `470`
- prototype: `__int64 __fastcall(TaskDefinitionImpl *__hidden this, struct TaskXmlWriter *, struct ITaskSettings3 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180002db0`

## callees

- `0x180001880`
- `0x180001b70`
- `0x180003a30`
- `0x180003f30`
- `0x1800145c0`
- `0x18003d034`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180001bf9`
- `OLEAUT32!__imp_SysFreeString` at `0x180001c0a`
- `OLEAUT32!__imp_SysFreeString` at `0x180001d14`
- `OLEAUT32!__imp_SysFreeString` at `0x180001d25`
- `OLEAUT32!__imp_SysFreeString` at `0x180001bf9`
- `OLEAUT32!__imp_SysFreeString` at `0x180001c0a`
- `OLEAUT32!__imp_SysFreeString` at `0x180001d14`
- `OLEAUT32!__imp_SysFreeString` at `0x180001d25`
- `OLEAUT32!__imp_SysStringLen` at `0x180001c59`
- `OLEAUT32!__imp_SysStringLen` at `0x180001ca7`
- `OLEAUT32!__imp_SysStringLen` at `0x180001c59`
- `OLEAUT32!__imp_SysStringLen` at `0x180001ca7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall TaskDefinitionImpl::WriteMaintenanceSettings(
        TaskDefinitionImpl *this,
        struct TaskXmlWriter *a2,
        struct ITaskSettings3 *a3)
{
  int started; // ebx
  __int64 v5; // r8
  BSTR pbstr[2]; // [rsp+20h] [rbp-10h] BYREF
  TaskDefinitionImpl *v8; // [rsp+50h] [rbp+20h] BYREF
  __int64 v9; // [rsp+60h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+38h] BYREF

  v8 = this;
  v9 = 0;
  started = ((__int64 (__fastcall *)(struct ITaskSettings3 *, __int64 *))a3->lpVtbl->get_MaintenanceSettings)(a3, &v9);
  if ( started < 0 )
  {
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    return (unsigned int)started;
  }
  if ( !v9 )
  {
LABEL_22:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
    return (unsigned int)started;
  }
  pbstr[0] = 0;
  bstrString = 0;
  LOWORD(v8) = 0;
  started = TaskXmlWriter::StartElement((int *)a2, (struct IErrorInfo *)0x88);
  if ( started >= 0 )
  {
    started = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v9 + 64LL))(v9, pbstr);
    if ( started >= 0 )
    {
      if ( !pbstr[0]
        || !SysStringLen(pbstr[0])
        || (started = TaskXmlWriter::Element((unsigned int *)a2, 137, (__int64)pbstr[0]), started >= 0) )
      {
        started = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v9 + 80LL))(v9, &bstrString);
        if ( started >= 0 )
        {
          if ( !bstrString
            || !SysStringLen(bstrString)
            || (started = TaskXmlWriter::Element((unsigned int *)a2, 138, (__int64)bstrString), started >= 0) )
          {
            started = (*(__int64 (__fastcall **)(__int64, TaskDefinitionImpl **))(*(_QWORD *)v9 + 96LL))(v9, &v8);
            if ( started >= 0 )
            {
              LOBYTE(v5) = (_WORD)v8 == 0xFFFF;
              started = TaskXmlWriter::ElementBool(a2, 139, v5);
              if ( started >= 0 )
                started = TaskXmlWriter::EndElement((__int64)a2);
            }
          }
        }
      }
    }
    SysFreeString(bstrString);
    SysFreeString(pbstr[0]);
    goto LABEL_22;
  }
  SysFreeString(bstrString);
  SysFreeString(pbstr[0]);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180001b70  mov     [rsp-18h+arg_0], rcx
0x180001b75  push    rbp
0x180001b76  push    rbx
0x180001b77  push    rdi
0x180001b78  mov     rbp, rsp
0x180001b7b  sub     rsp, 30h
0x180001b7f  mov     rdi, rdx
0x180001b82  mov     [rbp+arg_10], 0
0x180001b8a  mov     rax, [r8]
0x180001b8d  lea     rdx, [rbp+arg_10]
0x180001b91  mov     rcx, r8
0x180001b94  mov     rax, [rax+198h]
0x180001b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ba0  mov     ebx, eax
0x180001ba2  test    eax, eax
0x180001ba4  jns     short loc_180001BC1
0x180001ba6  mov     rcx, [rbp+arg_10]
0x180001baa  test    rcx, rcx
0x180001bad  jz      short loc_180001BBC
0x180001baf  mov     rdx, [rcx]
0x180001bb2  mov     rax, [rdx+10h]
0x180001bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bbb  nop
0x180001bbc  jmp     loc_180001D3B
0x180001bc1  cmp     [rbp+arg_10], 0
0x180001bc6  jz      loc_180001D32
0x180001bcc  mov     [rbp+pbstr], 0
0x180001bd4  mov     [rbp+bstrString], 0
0x180001bdc  xor     eax, eax
0x180001bde  mov     word ptr [rbp+arg_0], ax
0x180001be2  mov     edx, 88h
0x180001be7  mov     rcx, rdi
0x180001bea  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x180001bef  mov     ebx, eax
0x180001bf1  test    eax, eax
0x180001bf3  jns     short loc_180001C32
0x180001bf5  mov     rcx, [rbp+bstrString]; bstrString
0x180001bf9  call    cs:__imp_SysFreeString
0x180001c00  nop     dword ptr [rax+rax+00h]
0x180001c05  nop
0x180001c06  mov     rcx, [rbp+pbstr]; bstrString
0x180001c0a  call    cs:__imp_SysFreeString
0x180001c11  nop     dword ptr [rax+rax+00h]
0x180001c16  nop
0x180001c17  mov     rcx, [rbp+arg_10]
0x180001c1b  test    rcx, rcx
0x180001c1e  jz      short loc_180001C2D
0x180001c20  mov     rax, [rcx]
0x180001c23  mov     rax, [rax+10h]
0x180001c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c2c  nop
0x180001c2d  jmp     loc_180001D3B
0x180001c32  mov     rcx, [rbp+arg_10]
0x180001c36  mov     rax, [rcx]
0x180001c39  lea     rdx, [rbp+pbstr]
0x180001c3d  mov     rax, [rax+40h]
0x180001c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c46  mov     ebx, eax
0x180001c48  test    eax, eax
0x180001c4a  js      loc_180001D10
0x180001c50  mov     rcx, [rbp+pbstr]; pbstr
0x180001c54  test    rcx, rcx
0x180001c57  jz      short loc_180001C84
0x180001c59  call    cs:__imp_SysStringLen
0x180001c60  nop     dword ptr [rax+rax+00h]
0x180001c65  test    eax, eax
0x180001c67  jz      short loc_180001C84
0x180001c69  mov     r8, [rbp+pbstr]
0x180001c6d  mov     edx, 89h
0x180001c72  mov     rcx, rdi
0x180001c75  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180001c7a  mov     ebx, eax
0x180001c7c  test    eax, eax
0x180001c7e  js      loc_180001D10
0x180001c84  mov     rcx, [rbp+arg_10]
0x180001c88  mov     rax, [rcx]
0x180001c8b  lea     rdx, [rbp+bstrString]
0x180001c8f  mov     rax, [rax+50h]
0x180001c93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c98  mov     ebx, eax
0x180001c9a  test    eax, eax
0x180001c9c  js      short loc_180001D10
0x180001c9e  mov     rcx, [rbp+bstrString]; pbstr
0x180001ca2  test    rcx, rcx
0x180001ca5  jz      short loc_180001CCE
0x180001ca7  call    cs:__imp_SysStringLen
0x180001cae  nop     dword ptr [rax+rax+00h]
0x180001cb3  test    eax, eax
0x180001cb5  jz      short loc_180001CCE
0x180001cb7  mov     r8, [rbp+bstrString]
0x180001cbb  mov     edx, 8Ah
0x180001cc0  mov     rcx, rdi
0x180001cc3  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180001cc8  mov     ebx, eax
0x180001cca  test    eax, eax
0x180001ccc  js      short loc_180001D10
0x180001cce  mov     rcx, [rbp+arg_10]
0x180001cd2  mov     rax, [rcx]
0x180001cd5  lea     rdx, [rbp+arg_0]
0x180001cd9  mov     rax, [rax+60h]
0x180001cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ce2  mov     ebx, eax
0x180001ce4  test    eax, eax
0x180001ce6  js      short loc_180001D10
0x180001ce8  or      eax, 0FFFFFFFFh
0x180001ceb  cmp     ax, word ptr [rbp+arg_0]
0x180001cef  setz    r8b
0x180001cf3  mov     edx, 8Bh
0x180001cf8  mov     rcx, rdi
0x180001cfb  call    ?ElementBool@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@_N@Z; TaskXmlWriter::ElementBool(TaskXmlNodeId,bool)
0x180001d00  mov     ebx, eax
0x180001d02  test    eax, eax
0x180001d04  js      short loc_180001D10
0x180001d06  mov     rcx, rdi
0x180001d09  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x180001d0e  mov     ebx, eax
0x180001d10  mov     rcx, [rbp+bstrString]; bstrString
0x180001d14  call    cs:__imp_SysFreeString
0x180001d1b  nop     dword ptr [rax+rax+00h]
0x180001d20  nop
0x180001d21  mov     rcx, [rbp+pbstr]; bstrString
0x180001d25  call    cs:__imp_SysFreeString
0x180001d2c  nop     dword ptr [rax+rax+00h]
0x180001d31  nop
0x180001d32  lea     rcx, [rbp+arg_10]
0x180001d36  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001d3b  mov     eax, ebx
0x180001d3d  add     rsp, 30h
0x180001d41  pop     rdi
0x180001d42  pop     rbx
0x180001d43  pop     rbp
0x180001d44  retn
```
