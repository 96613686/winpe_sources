# _anonymous_namespace_::CancelThread

- ea: `0x140063700`
- end: `0x140063786`
- name: `_anonymous_namespace_::CancelThread`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14006378c`
- `0x140063ee4`

## callees

- `0x140063700`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!QueueUserAPC` at `0x14006376b`
- `KERNEL32!QueueUserAPC` at `0x14006376b`
- `KERNEL32!OpenThread` at `0x140063750`
- `KERNEL32!OpenThread` at `0x140063750`
- `KERNEL32!CloseHandle` at `0x14006377a`
- `KERNEL32!CloseHandle` at `0x14006377a`
- `USER32!PostThreadMessageW` at `0x140063742`
- `USER32!PostThreadMessageW` at `0x140063742`

## pseudocode

```c
int __fastcall anonymous_namespace_::CancelThread(__int64 a1)
{
  __int64 v2; // rcx
  HANDLE v3; // rax
  void *v4; // rbx

  _InterlockedExchange((volatile __int32 *)(a1 + 12), 1);
  v2 = *(_QWORD *)(a1 + 72);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  if ( *(_BYTE *)(a1 + 9) )
    PostThreadMessageW(*(_DWORD *)a1, 0, 0, 0);
  v3 = OpenThread(0x10u, 0, *(_DWORD *)a1);
  v4 = v3;
  if ( v3 )
  {
    LODWORD(v3) = QueueUserAPC(Com::Module::Initialize, v3, 0);
    if ( v4 != (void *)-1LL )
      LODWORD(v3) = CloseHandle(v4);
  }
  return (int)v3;
}

```

## disassembly

```asm
0x140063700  push    rbx
0x140063702  sub     rsp, 20h
0x140063706  mov     [rsp+28h+arg_0], 0
0x14006370e  mov     rbx, rcx
0x140063711  mov     byte ptr [rsp+28h+arg_0], 1
0x140063716  mov     eax, [rsp+28h+arg_0]
0x14006371a  xchg    eax, [rcx+0Ch]
0x14006371d  mov     rcx, [rcx+48h]
0x140063721  test    rcx, rcx
0x140063724  jz      short loc_140063732
0x140063726  mov     rax, [rcx]
0x140063729  mov     rax, [rax+10h]
0x14006372d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140063732  cmp     byte ptr [rbx+9], 0
0x140063736  jz      short loc_140063748
0x140063738  mov     ecx, [rbx]; idThread
0x14006373a  xor     r9d, r9d; lParam
0x14006373d  xor     r8d, r8d; wParam
0x140063740  xor     edx, edx; Msg
0x140063742  call    cs:__imp_PostThreadMessageW
0x140063748  mov     r8d, [rbx]; dwThreadId
0x14006374b  xor     edx, edx; bInheritHandle
0x14006374d  lea     ecx, [rdx+10h]; dwDesiredAccess
0x140063750  call    cs:__imp_OpenThread
0x140063756  mov     rbx, rax
0x140063759  test    rax, rax
0x14006375c  jz      short loc_140063780
0x14006375e  xor     r8d, r8d; dwData
0x140063761  lea     rcx, ?Initialize@Module@Com@@MEAAXXZ; pfnAPC
0x140063768  mov     rdx, rax; hThread
0x14006376b  call    cs:__imp_QueueUserAPC
0x140063771  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140063775  jz      short loc_140063780
0x140063777  mov     rcx, rbx; hObject
0x14006377a  call    cs:__imp_CloseHandle
0x140063780  add     rsp, 20h
0x140063784  pop     rbx
0x140063785  retn
```
