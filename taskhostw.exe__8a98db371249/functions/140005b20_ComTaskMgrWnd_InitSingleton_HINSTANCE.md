# ComTaskMgrWnd::InitSingleton(HINSTANCE__ *)

- ea: `0x140005b20`
- end: `0x140005b46`
- name: `?InitSingleton@ComTaskMgrWnd@@UEAAJPEAUHINSTANCE__@@@Z`
- size: `38`
- prototype: `__int64 __fastcall(ComTaskMgrWnd *__hidden this, HINSTANCE)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x140005b20`
- `0x140005b50`

## pseudocode

```c
__int64 __fastcall ComTaskMgrWnd::InitSingleton(ComTaskMgrWnd *this, HINSTANCE a2)
{
  __int64 result; // rax

  *((_QWORD *)this + 1) = a2;
  result = ComTaskMgrWnd::CreateMsgPumpThread(this);
  if ( (int)result < 0 )
    *((_QWORD *)this + 1) = 0;
  return result;
}

```

## disassembly

```asm
0x140005b20  push    rbx
0x140005b22  sub     rsp, 20h
0x140005b26  mov     rbx, rcx
0x140005b29  mov     [rcx+8], rdx
0x140005b2d  call    ?CreateMsgPumpThread@ComTaskMgrWnd@@AEAAJXZ; ComTaskMgrWnd::CreateMsgPumpThread(void)
0x140005b32  test    eax, eax
0x140005b34  js      short loc_140005B3C
0x140005b36  add     rsp, 20h
0x140005b3a  pop     rbx
0x140005b3b  retn
0x140005b3c  mov     qword ptr [rbx+8], 0
0x140005b44  jmp     short loc_140005B36
```
