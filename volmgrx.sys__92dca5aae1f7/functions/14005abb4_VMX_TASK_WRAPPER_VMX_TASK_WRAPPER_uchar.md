# VMX_TASK_WRAPPER::VMX_TASK_WRAPPER(uchar)

- ea: `0x14005abb4`
- end: `0x14005abfb`
- name: `??0VMX_TASK_WRAPPER@@QEAA@E@Z`
- size: `71`
- prototype: `VMX_TASK_WRAPPER *__fastcall(VMX_TASK_WRAPPER *__hidden this, unsigned __int8)`
- caller_count: `34`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x14002b964`
- `0x14002fec0`
- `0x140030110`
- `0x1400302dc`
- `0x140030680`
- `0x140030a04`
- `0x140031180`
- `0x140031390`
- `0x140031530`
- `0x140035180`
- `0x140035544`
- `0x140035e3c`
- `0x1400362a8`
- `0x14003677c`
- `0x140036bac`
- `0x140036e70`
- `0x140037fe4`
- `0x140038468`
- `0x140038d44`
- `0x1400397a0`
- `0x140039820`
- `0x140039d00`
- `0x140039f10`
- `0x14003ae9c`
- `0x14003aefc`
- `0x14003b094`
- `0x14003b350`
- `0x14003b600`
- `0x14003bc30`
- `0x14003bd90`
- `0x14003c660`
- `0x14003c870`
- `0x14003ccc0`
- `0x14005b250`

## callees

- `0x14001b9a0`
- `0x14005abb4`

## pseudocode

```c
VMX_TASK_WRAPPER *__fastcall VMX_TASK_WRAPPER::VMX_TASK_WRAPPER(VMX_TASK_WRAPPER *this, char a2)
{
  __int64 v3; // rcx

  *(_BYTE *)this = a2;
  if ( a2 )
    (*((void (__fastcall **)(_QWORD))Global + 5))(*((_QWORD *)Global + 1));
  v3 = *((_QWORD *)Global + 36);
  if ( *(_QWORD *)(v3 + 40) != v3 + 40 )
    ++*(_DWORD *)(v3 + 4);
  return this;
}

```

## disassembly

```asm
0x14005abb4  push    rbx
0x14005abb6  sub     rsp, 20h
0x14005abba  mov     [rcx], dl
0x14005abbc  mov     rbx, rcx
0x14005abbf  test    dl, dl
0x14005abc1  jz      short loc_14005ABD7
0x14005abc3  mov     rcx, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14005abca  mov     rax, [rcx+28h]
0x14005abce  mov     rcx, [rcx+8]
0x14005abd2  call    _guard_dispatch_icall
0x14005abd7  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14005abde  mov     rcx, [rax+120h]
0x14005abe5  lea     rax, [rcx+28h]
0x14005abe9  cmp     [rax], rax
0x14005abec  jz      short loc_14005ABF1
0x14005abee  inc     dword ptr [rcx+4]
0x14005abf1  mov     rax, rbx
0x14005abf4  add     rsp, 20h
0x14005abf8  pop     rbx
0x14005abf9  retn
```
