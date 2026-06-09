# TaskDefinitionImpl::WriteMaintenanceSettings(TaskXmlWriter &,ITaskSettings3 *)

- ea: `0x180001b00`
- end: `0x180001cb1`
- name: `?WriteMaintenanceSettings@TaskDefinitionImpl@@AEAAJAEAVTaskXmlWriter@@PEAUITaskSettings3@@@Z`
- size: `433`
- prototype: `__int64 __fastcall(TaskDefinitionImpl *__hidden this, struct TaskXmlWriter *, struct ITaskSettings3 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180002c10`

## callees

- `0x1800017f0`
- `0x180001b00`
- `0x180003840`
- `0x180003d1c`
- `0x1800136e0`
- `0x180039e34`
- `0x180054010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180001b89`
- `OLEAUT32!__imp_SysFreeString` at `0x180001b94`
- `OLEAUT32!__imp_SysFreeString` at `0x180001c8c`
- `OLEAUT32!__imp_SysFreeString` at `0x180001c97`
- `OLEAUT32!__imp_SysFreeString` at `0x180001b89`
- `OLEAUT32!__imp_SysFreeString` at `0x180001b94`
- `OLEAUT32!__imp_SysFreeString` at `0x180001c8c`
- `OLEAUT32!__imp_SysFreeString` at `0x180001c97`
- `OLEAUT32!__imp_SysStringLen` at `0x180001bdd`
- `OLEAUT32!__imp_SysStringLen` at `0x180001c25`
- `OLEAUT32!__imp_SysStringLen` at `0x180001bdd`
- `OLEAUT32!__imp_SysStringLen` at `0x180001c25`

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
0x180001b00  mov     [rsp-18h+arg_0], rcx
0x180001b05  push    rbp
0x180001b06  push    rbx
0x180001b07  push    rdi
0x180001b08  mov     rbp, rsp
0x180001b0b  sub     rsp, 30h
0x180001b0f  mov     rdi, rdx
0x180001b12  mov     [rbp+arg_10], 0
0x180001b1a  mov     rax, [r8]
0x180001b1d  lea     rdx, [rbp+arg_10]
0x180001b21  mov     rcx, r8
0x180001b24  mov     rax, [rax+198h]
0x180001b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b30  mov     ebx, eax
0x180001b32  test    eax, eax
0x180001b34  jns     short loc_180001B51
0x180001b36  mov     rcx, [rbp+arg_10]
0x180001b3a  test    rcx, rcx
0x180001b3d  jz      short loc_180001B4C
0x180001b3f  mov     rdx, [rcx]
0x180001b42  mov     rax, [rdx+10h]
0x180001b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b4b  nop
0x180001b4c  jmp     loc_180001CA7
0x180001b51  cmp     [rbp+arg_10], 0
0x180001b56  jz      loc_180001C9E
0x180001b5c  mov     [rbp+pbstr], 0
0x180001b64  mov     [rbp+bstrString], 0
0x180001b6c  xor     eax, eax
0x180001b6e  mov     word ptr [rbp+arg_0], ax
0x180001b72  mov     edx, 88h
0x180001b77  mov     rcx, rdi
0x180001b7a  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x180001b7f  mov     ebx, eax
0x180001b81  test    eax, eax
0x180001b83  jns     short loc_180001BB6
0x180001b85  mov     rcx, [rbp+bstrString]; bstrString
0x180001b89  call    cs:__imp_SysFreeString
0x180001b8f  nop
0x180001b90  mov     rcx, [rbp+pbstr]; bstrString
0x180001b94  call    cs:__imp_SysFreeString
0x180001b9a  nop
0x180001b9b  mov     rcx, [rbp+arg_10]
0x180001b9f  test    rcx, rcx
0x180001ba2  jz      short loc_180001BB1
0x180001ba4  mov     rax, [rcx]
0x180001ba7  mov     rax, [rax+10h]
0x180001bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bb0  nop
0x180001bb1  jmp     loc_180001CA7
0x180001bb6  mov     rcx, [rbp+arg_10]
0x180001bba  mov     rax, [rcx]
0x180001bbd  lea     rdx, [rbp+pbstr]
0x180001bc1  mov     rax, [rax+40h]
0x180001bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bca  mov     ebx, eax
0x180001bcc  test    eax, eax
0x180001bce  js      loc_180001C88
0x180001bd4  mov     rcx, [rbp+pbstr]; pbstr
0x180001bd8  test    rcx, rcx
0x180001bdb  jz      short loc_180001C02
0x180001bdd  call    cs:__imp_SysStringLen
0x180001be3  test    eax, eax
0x180001be5  jz      short loc_180001C02
0x180001be7  mov     r8, [rbp+pbstr]
0x180001beb  mov     edx, 89h
0x180001bf0  mov     rcx, rdi
0x180001bf3  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180001bf8  mov     ebx, eax
0x180001bfa  test    eax, eax
0x180001bfc  js      loc_180001C88
0x180001c02  mov     rcx, [rbp+arg_10]
0x180001c06  mov     rax, [rcx]
0x180001c09  lea     rdx, [rbp+bstrString]
0x180001c0d  mov     rax, [rax+50h]
0x180001c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c16  mov     ebx, eax
0x180001c18  test    eax, eax
0x180001c1a  js      short loc_180001C88
0x180001c1c  mov     rcx, [rbp+bstrString]; pbstr
0x180001c20  test    rcx, rcx
0x180001c23  jz      short loc_180001C46
0x180001c25  call    cs:__imp_SysStringLen
0x180001c2b  test    eax, eax
0x180001c2d  jz      short loc_180001C46
0x180001c2f  mov     r8, [rbp+bstrString]
0x180001c33  mov     edx, 8Ah
0x180001c38  mov     rcx, rdi
0x180001c3b  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180001c40  mov     ebx, eax
0x180001c42  test    eax, eax
0x180001c44  js      short loc_180001C88
0x180001c46  mov     rcx, [rbp+arg_10]
0x180001c4a  mov     rax, [rcx]
0x180001c4d  lea     rdx, [rbp+arg_0]
0x180001c51  mov     rax, [rax+60h]
0x180001c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c5a  mov     ebx, eax
0x180001c5c  test    eax, eax
0x180001c5e  js      short loc_180001C88
0x180001c60  or      eax, 0FFFFFFFFh
0x180001c63  cmp     ax, word ptr [rbp+arg_0]
0x180001c67  setz    r8b
0x180001c6b  mov     edx, 8Bh
0x180001c70  mov     rcx, rdi
0x180001c73  call    ?ElementBool@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@_N@Z; TaskXmlWriter::ElementBool(TaskXmlNodeId,bool)
0x180001c78  mov     ebx, eax
0x180001c7a  test    eax, eax
0x180001c7c  js      short loc_180001C88
0x180001c7e  mov     rcx, rdi
0x180001c81  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x180001c86  mov     ebx, eax
0x180001c88  mov     rcx, [rbp+bstrString]; bstrString
0x180001c8c  call    cs:__imp_SysFreeString
0x180001c92  nop
0x180001c93  mov     rcx, [rbp+pbstr]; bstrString
0x180001c97  call    cs:__imp_SysFreeString
0x180001c9d  nop
0x180001c9e  lea     rcx, [rbp+arg_10]
0x180001ca2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001ca7  mov     eax, ebx
0x180001ca9  add     rsp, 30h
0x180001cad  pop     rdi
0x180001cae  pop     rbx
0x180001caf  pop     rbp
0x180001cb0  retn
```
