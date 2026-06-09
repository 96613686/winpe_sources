# RunService(ulong,ushort * *)

- ea: `0x1800062c8`
- end: `0x180006373`
- name: `?RunService@@YAXKPEAPEAG@Z`
- size: `171`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b760`

## callees

- `0x180005a60`
- `0x1800062c8`
- `0x18000637c`
- `0x18001d3a0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000632f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000632f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000634c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000634c`

## pseudocode

```c
void __fastcall RunService(unsigned int a1, unsigned __int16 **a2)
{
  _QWORD v4[2]; // [rsp+30h] [rbp-68h] BYREF
  void *v5; // [rsp+40h] [rbp-58h]
  HANDLE hObject; // [rsp+70h] [rbp-28h]

  MyService::MyService((MyService *)v4, (unsigned int)a2);
  CNtService::Run((CNtService *)v4, L"winmgmt", a1, a2, v4);
  v4[0] = &MyService::`vftable';
  if ( hObject )
    CloseHandle(hObject);
  v4[0] = &CNtService::`vftable';
  if ( v5 )
    CWin32DefaultArena::WbemMemFree(v5);
}

```

## disassembly

```asm
0x1800062c8  mov     [rsp+arg_10], rbx
0x1800062cd  push    rdi
0x1800062ce  sub     rsp, 90h
0x1800062d5  mov     rax, cs:__security_cookie
0x1800062dc  xor     rax, rsp
0x1800062df  mov     [rsp+98h+var_18], rax
0x1800062e7  mov     rdi, rdx
0x1800062ea  mov     ebx, ecx
0x1800062ec  lea     rcx, [rsp+98h+var_68]; this
0x1800062f1  call    ??0MyService@@QEAA@K@Z; MyService::MyService(ulong)
0x1800062f6  nop
0x1800062f7  lea     rax, [rsp+98h+var_68]
0x1800062fc  mov     [rsp+98h+var_78], rax; void *
0x180006301  mov     r9, rdi; unsigned __int16 **
0x180006304  mov     r8d, ebx; unsigned int
0x180006307  lea     rdx, ServiceName; "winmgmt"
0x18000630e  lea     rcx, [rsp+98h+var_68]; this
0x180006313  call    ?Run@CNtService@@UEAAKPEAGKPEAPEAGPEAX@Z; CNtService::Run(ushort *,ulong,ushort * *,void *)
0x180006318  nop
0x180006319  lea     rax, ??_7MyService@@6B@; const MyService::`vftable'
0x180006320  mov     [rsp+98h+var_68], rax
0x180006325  mov     rcx, [rsp+98h+hObject]; hObject
0x18000632a  test    rcx, rcx
0x18000632d  jz      short loc_180006336
0x18000632f  call    cs:__imp_CloseHandle
0x180006335  nop
0x180006336  lea     rax, ??_7CNtService@@6B@; const CNtService::`vftable'
0x18000633d  mov     [rsp+98h+var_68], rax
0x180006342  mov     rcx, [rsp+98h+var_58]
0x180006347  test    rcx, rcx
0x18000634a  jz      short loc_180006352
0x18000634c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180006352  mov     rcx, [rsp+98h+var_18]
0x18000635a  xor     rcx, rsp; StackCookie
0x18000635d  call    __security_check_cookie
0x180006362  mov     rbx, [rsp+98h+arg_10]
0x18000636a  add     rsp, 90h
0x180006371  pop     rdi
0x180006372  retn
```
