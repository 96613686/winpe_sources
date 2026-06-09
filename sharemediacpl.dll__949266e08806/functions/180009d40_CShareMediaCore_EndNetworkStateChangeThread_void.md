# CShareMediaCore::EndNetworkStateChangeThread(void)

- ea: `0x180009d40`
- end: `0x180009def`
- name: `?EndNetworkStateChangeThread@CShareMediaCore@@QEAAJXZ`
- size: `175`
- prototype: `__int64 __fastcall(CShareMediaCore *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180007e5c`
- `0x18000c3d0`
- `0x18000dba8`

## callees

- `0x180003860`
- `0x180003888`
- `0x180009d40`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180009db2`
- `KERNEL32!WaitForSingleObject` at `0x180009db2`
- `KERNEL32!SetEvent` at `0x180009d91`
- `KERNEL32!SetEvent` at `0x180009d91`

## pseudocode

```c
__int64 __fastcall CShareMediaCore::EndNetworkStateChangeThread(HANDLE *this)
{
  _QWORD *v2; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( this[22] )
  {
    SetEvent(this[22]);
    v2 = WPP_GLOBAL_Control;
  }
  if ( this[20] )
  {
    WaitForSingleObject(this[20], 0x7D0u);
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
    WPP_SF_d(v2[2], 27, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x180009d40  mov     [rsp+arg_0], rbx
0x180009d45  push    rdi
0x180009d46  sub     rsp, 20h
0x180009d4a  mov     rbx, rcx
0x180009d4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d54  lea     rdi, WPP_GLOBAL_Control
0x180009d5b  cmp     rcx, rdi
0x180009d5e  jz      short loc_180009D82
0x180009d60  test    byte ptr [rcx+1Ch], 20h
0x180009d64  jz      short loc_180009D82
0x180009d66  mov     rcx, [rcx+10h]
0x180009d6a  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180009d71  mov     edx, 1Ah
0x180009d76  call    WPP_SF_
0x180009d7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d82  mov     rax, [rbx+0B0h]
0x180009d89  test    rax, rax
0x180009d8c  jz      short loc_180009D9E
0x180009d8e  mov     rcx, rax; hEvent
0x180009d91  call    cs:__imp_SetEvent
0x180009d97  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d9e  mov     rax, [rbx+0A0h]
0x180009da5  test    rax, rax
0x180009da8  jz      short loc_180009DBF
0x180009daa  mov     edx, 7D0h; dwMilliseconds
0x180009daf  mov     rcx, rax; hHandle
0x180009db2  call    cs:__imp_WaitForSingleObject
0x180009db8  mov     rcx, cs:WPP_GLOBAL_Control
0x180009dbf  cmp     rcx, rdi
0x180009dc2  jz      short loc_180009DE2
0x180009dc4  test    byte ptr [rcx+1Ch], 20h
0x180009dc8  jz      short loc_180009DE2
0x180009dca  mov     rcx, [rcx+10h]
0x180009dce  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180009dd5  mov     edx, 1Bh
0x180009dda  xor     r9d, r9d
0x180009ddd  call    WPP_SF_d
0x180009de2  mov     rbx, [rsp+28h+arg_0]
0x180009de7  xor     eax, eax
0x180009de9  add     rsp, 20h
0x180009ded  pop     rdi
0x180009dee  retn
```
