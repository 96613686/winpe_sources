# FrameProvider::Release(void)

- ea: `0x180018050`
- end: `0x18001807b`
- name: `?Release@FrameProvider@@UEAAKXZ`
- size: `43`
- prototype: `unsigned int __fastcall(FrameProvider *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180018090`
- `0x1800180a0`
- `0x1800180b0`
- `0x1800180c0`
- `0x1800180d0`

## callees

- `0x180018050`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall FrameProvider::Release(FrameProvider *this)
{
  bool v1; // zf
  unsigned int v2; // ebx

  v1 = (*((_DWORD *)this + 4))-- == 1;
  v2 = *((_DWORD *)this + 4);
  if ( v1 )
    (*(void (__fastcall **)(FrameProvider *, __int64))(*(_QWORD *)this + 144LL))(this, 1);
  return v2;
}

```

## disassembly

```asm
0x180018050  push    rbx
0x180018052  sub     rsp, 20h
0x180018056  sub     dword ptr [rcx+10h], 1
0x18001805a  mov     ebx, [rcx+10h]
0x18001805d  jnz     short loc_180018073
0x18001805f  mov     rdx, [rcx]
0x180018062  mov     rax, [rdx+90h]
0x180018069  mov     edx, 1
0x18001806e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018073  mov     eax, ebx
0x180018075  add     rsp, 20h
0x180018079  pop     rbx
0x18001807a  retn
```
