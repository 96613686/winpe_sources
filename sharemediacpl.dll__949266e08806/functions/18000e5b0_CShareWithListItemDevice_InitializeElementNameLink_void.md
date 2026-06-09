# CShareWithListItemDevice::_InitializeElementNameLink(void)

- ea: `0x18000e5b0`
- end: `0x18000e636`
- name: `?_InitializeElementNameLink@CShareWithListItemDevice@@EEAAJXZ`
- size: `134`
- prototype: `__int64 __fastcall(CShareWithListItemDevice *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180003860`
- `0x180003888`
- `0x18000e5b0`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CShareWithListItemDevice::_InitializeElementNameLink(CShareWithListItemDevice *this)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 247, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  v2 = (*(__int64 (__fastcall **)(CShareWithListItemDevice *))(*(_QWORD *)this + 408LL))(this);
  v3 = v2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 248, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, v2);
  return v3;
}

```

## disassembly

```asm
0x18000e5b0  mov     [rsp+arg_0], rbx
0x18000e5b5  push    rdi
0x18000e5b6  sub     rsp, 20h
0x18000e5ba  mov     rbx, rcx
0x18000e5bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e5c4  lea     rdi, WPP_GLOBAL_Control
0x18000e5cb  cmp     rcx, rdi
0x18000e5ce  jz      short loc_18000E5EB
0x18000e5d0  test    byte ptr [rcx+1Ch], 20h
0x18000e5d4  jz      short loc_18000E5EB
0x18000e5d6  mov     rcx, [rcx+10h]
0x18000e5da  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000e5e1  mov     edx, 0F7h
0x18000e5e6  call    WPP_SF_
0x18000e5eb  mov     rax, [rbx]
0x18000e5ee  mov     rcx, rbx
0x18000e5f1  mov     rax, [rax+198h]
0x18000e5f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5fd  mov     ebx, eax
0x18000e5ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e606  cmp     rcx, rdi
0x18000e609  jz      short loc_18000E629
0x18000e60b  test    byte ptr [rcx+1Ch], 20h
0x18000e60f  jz      short loc_18000E629
0x18000e611  mov     rcx, [rcx+10h]
0x18000e615  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000e61c  mov     edx, 0F8h
0x18000e621  mov     r9d, eax
0x18000e624  call    WPP_SF_d
0x18000e629  mov     eax, ebx
0x18000e62b  mov     rbx, [rsp+28h+arg_0]
0x18000e630  add     rsp, 20h
0x18000e634  pop     rdi
0x18000e635  retn
```
