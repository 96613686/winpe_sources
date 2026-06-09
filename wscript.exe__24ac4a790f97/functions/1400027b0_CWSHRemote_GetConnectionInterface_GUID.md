# CWSHRemote::GetConnectionInterface(_GUID *)

- ea: `0x1400027b0`
- end: `0x1400027f5`
- name: `?GetConnectionInterface@CWSHRemote@@UEAAJPEAU_GUID@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(CWSHRemote *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1400027b0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400027cc`
- `KERNEL32!GetCurrentThreadId` at `0x1400027cc`

## pseudocode

```c
__int64 __fastcall CWSHRemote::GetConnectionInterface(CWSHRemote *this, struct _GUID *a2)
{
  __int64 result; // rax
  int v4; // ebx

  if ( !a2 )
    return 2147500035LL;
  v4 = *((_DWORD *)this + 4);
  if ( GetCurrentThreadId() != v4 )
    return 2147549183LL;
  result = 0;
  *a2 = IID_IDispatch;
  return result;
}

```

## disassembly

```asm
0x1400027b0  mov     [rsp+arg_0], rbx
0x1400027b5  push    rdi
0x1400027b6  sub     rsp, 20h
0x1400027ba  mov     rdi, rdx
0x1400027bd  test    rdx, rdx
0x1400027c0  jnz     short loc_1400027C9
0x1400027c2  mov     eax, 80004003h
0x1400027c7  jmp     short loc_1400027EA
0x1400027c9  mov     ebx, [rcx+10h]
0x1400027cc  call    cs:__imp_GetCurrentThreadId
0x1400027d2  cmp     eax, ebx
0x1400027d4  jz      short loc_1400027DD
0x1400027d6  mov     eax, 8000FFFFh
0x1400027db  jmp     short loc_1400027EA
0x1400027dd  movups  xmm0, xmmword ptr cs:IID_IDispatch.Data1
0x1400027e4  xor     eax, eax
0x1400027e6  movdqu  xmmword ptr [rdi], xmm0
0x1400027ea  mov     rbx, [rsp+28h+arg_0]
0x1400027ef  add     rsp, 20h
0x1400027f3  pop     rdi
0x1400027f4  retn
```
