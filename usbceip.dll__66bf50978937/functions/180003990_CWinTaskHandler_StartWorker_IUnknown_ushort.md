# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x180003990`
- end: `0x1800039e0`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180003204`
- `0x180003990`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800039b4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800039b4`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::StartWorker(CWinTaskHandler *this, struct IUnknown *a2, unsigned __int16 *a3)
{
  __int64 v6; // rax

  if ( !a2 )
    return 2147942487LL;
  if ( !a3 )
    return CWinTaskHandler::CreateWorkerThread(this, a2);
  v6 = _o__wcsdup(a3);
  *((_QWORD *)this + 1) = v6;
  if ( v6 )
    return CWinTaskHandler::CreateWorkerThread(this, a2);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180003990  mov     [rsp+arg_0], rbx
0x180003995  push    rdi
0x180003996  sub     rsp, 20h
0x18000399a  mov     rdi, rdx
0x18000399d  mov     rbx, rcx
0x1800039a0  test    rdx, rdx
0x1800039a3  jnz     short loc_1800039AC
0x1800039a5  mov     eax, 80070057h
0x1800039aa  jmp     short loc_1800039D5
0x1800039ac  test    r8, r8
0x1800039af  jz      short loc_1800039CA
0x1800039b1  mov     rcx, r8
0x1800039b4  call    cs:__imp__o__wcsdup
0x1800039ba  mov     [rbx+8], rax
0x1800039be  test    rax, rax
0x1800039c1  jnz     short loc_1800039CA
0x1800039c3  mov     eax, 8007000Eh
0x1800039c8  jmp     short loc_1800039D5
0x1800039ca  mov     rdx, rdi; struct IUnknown *
0x1800039cd  mov     rcx, rbx; this
0x1800039d0  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x1800039d5  mov     rbx, [rsp+28h+arg_0]
0x1800039da  add     rsp, 20h
0x1800039de  pop     rdi
0x1800039df  retn
```
