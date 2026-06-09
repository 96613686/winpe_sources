# UninitializeComTasksLib

- ea: `0x140001c00`
- end: `0x140001d1b`
- name: `UninitializeComTasksLib`
- size: `283`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400012b0`

## callees

- `0x140001c00`
- `0x140009330`
- `0x140009400`
- `0x14000c010`

## pseudocode

```c
__int64 UninitializeComTasksLib()
{
  int v0; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12);
  v0 = 0;
  if ( ComTaskMgrBase::s_pVirtualSingleton )
  {
    v0 = (*(__int64 (**)(void))(*(_QWORD *)ComTaskMgrBase::s_pVirtualSingleton + 48LL))();
    if ( ComTaskMgrBase::s_pVirtualSingleton )
      (*(void (__fastcall **)(ComTaskMgrWnd *, __int64))(*(_QWORD *)ComTaskMgrBase::s_pVirtualSingleton + 32LL))(
        ComTaskMgrBase::s_pVirtualSingleton,
        1);
    ComTaskMgrBase::s_pVirtualSingleton = 0;
  }
  if ( v0 >= 0 )
    return 0;
  v0 = (unsigned __int16)v0;
  if ( !(_WORD)v0 )
    v0 = 6;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_fd76d537424c3f213087d14e42e29f74_Traceguids, (unsigned int)v0);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x140001c00  mov     [rsp+arg_8], rbx
0x140001c05  push    rdi
0x140001c06  sub     rsp, 30h
0x140001c0a  lea     rdi, WPP_GLOBAL_Control
0x140001c11  mov     rcx, cs:WPP_GLOBAL_Control
0x140001c18  cmp     rcx, rdi
0x140001c1b  jz      short loc_140001C23
0x140001c1d  test    byte ptr [rcx+1Ch], 4
0x140001c21  jnz     short loc_140001C78
0x140001c23  xor     ebx, ebx
0x140001c25  mov     rcx, cs:?s_pVirtualSingleton@ComTaskMgrBase@@0PEAV1@EA; ComTaskMgrBase * ComTaskMgrBase::s_pVirtualSingleton
0x140001c2c  test    rcx, rcx
0x140001c2f  jz      short loc_140001C67
0x140001c31  mov     rax, [rcx]
0x140001c34  mov     rax, [rax+30h]
0x140001c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001c3d  mov     ebx, eax
0x140001c3f  mov     rcx, cs:?s_pVirtualSingleton@ComTaskMgrBase@@0PEAV1@EA; ComTaskMgrBase * ComTaskMgrBase::s_pVirtualSingleton
0x140001c46  test    rcx, rcx
0x140001c49  jz      short loc_140001C5C
0x140001c4b  mov     rax, [rcx]
0x140001c4e  mov     edx, 1
0x140001c53  mov     rax, [rax+20h]
0x140001c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001c5c  mov     cs:?s_pVirtualSingleton@ComTaskMgrBase@@0PEAV1@EA, 0; ComTaskMgrBase * ComTaskMgrBase::s_pVirtualSingleton
0x140001c67  test    ebx, ebx
0x140001c69  js      short loc_140001CDD
0x140001c6b  xor     eax, eax
0x140001c6d  mov     rbx, [rsp+38h+arg_8]
0x140001c72  add     rsp, 30h
0x140001c76  pop     rdi
0x140001c77  retn
0x140001c78  mov     edx, 0Ch
0x140001c7d  mov     rcx, [rcx+10h]
0x140001c81  call    WPP_SF_
0x140001c86  jmp     short loc_140001C23
0x140001c88  jmp     short loc_140001CD0
0x140001c8a  mov     ebx, 4005h
0x140001c8f  lea     rdi, WPP_GLOBAL_Control
0x140001c96  jmp     short loc_140001CEA
0x140001c98  mov     ebx, 57h ; 'W'
0x140001c9d  lea     rdi, WPP_GLOBAL_Control
0x140001ca4  jmp     short loc_140001CEA
0x140001ca6  mov     ebx, 57h ; 'W'
0x140001cab  lea     rdi, WPP_GLOBAL_Control
0x140001cb2  jmp     short loc_140001CEA
0x140001cb4  mov     ebx, 57h ; 'W'
0x140001cb9  lea     rdi, WPP_GLOBAL_Control
0x140001cc0  jmp     short loc_140001CEA
0x140001cc2  mov     ebx, 0Eh
0x140001cc7  lea     rdi, WPP_GLOBAL_Control
0x140001cce  jmp     short loc_140001CEA
0x140001cd0  mov     ebx, [rsp+38h+arg_0]
0x140001cd4  lea     rdi, WPP_GLOBAL_Control
0x140001cdb  jmp     short loc_140001C67
0x140001cdd  movzx   ebx, bx
0x140001ce0  mov     eax, 6
0x140001ce5  test    ebx, ebx
0x140001ce7  cmovz   ebx, eax
0x140001cea  mov     rcx, cs:WPP_GLOBAL_Control
0x140001cf1  cmp     rcx, rdi
0x140001cf4  jz      short loc_140001D14
0x140001cf6  test    byte ptr [rcx+1Ch], 1
0x140001cfa  jz      short loc_140001D14
0x140001cfc  mov     edx, 0Dh
0x140001d01  mov     r9d, ebx
0x140001d04  lea     r8, WPP_fd76d537424c3f213087d14e42e29f74_Traceguids
0x140001d0b  mov     rcx, [rcx+10h]
0x140001d0f  call    WPP_SF_d
0x140001d14  mov     eax, ebx
0x140001d16  jmp     loc_140001C6D
```
