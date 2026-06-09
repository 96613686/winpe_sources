# CThemeManagerDispatcher::CreateAndExecuteRequest(CPortMessage const &)

- ea: `0x18000cd60`
- end: `0x18000cdfc`
- name: `?CreateAndExecuteRequest@CThemeManagerDispatcher@@UEAAJAEBVCPortMessage@@@Z`
- size: `156`
- prototype: `__int64 __fastcall(CThemeManagerDispatcher *__hidden this, const struct CPortMessage *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180005ac0`
- `0x180006698`
- `0x18000cd60`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cd7c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cd7c`

## pseudocode

```c
__int64 __fastcall CThemeManagerDispatcher::CreateAndExecuteRequest(
        CThemeManagerDispatcher *this,
        const struct CPortMessage *a2)
{
  CAPIRequest *v4; // rax
  struct CAPIRequest *v5; // rbx
  unsigned int v6; // edi

  v4 = (CAPIRequest *)LocalAlloc(0, 0xA0u);
  v5 = v4;
  if ( v4 )
  {
    CAPIRequest::CAPIRequest(v4, this, a2);
    *((_QWORD *)v5 + 18) = 0;
    *(_QWORD *)v5 = &CThemeManagerAPIRequest::`vftable'{for `CQueueElement'};
    *((_QWORD *)v5 + 2) = &CThemeManagerAPIRequest::`vftable'{for `CPortMessage'};
    *((_QWORD *)v5 + 19) = 0;
    v6 = CAPIDispatcher::Execute(this, v5);
    (**(void (__fastcall ***)(struct CAPIRequest *, __int64))v5)(v5, 1);
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return v6;
}

```

## disassembly

```asm
0x18000cd60  mov     [rsp+arg_0], rbx
0x18000cd65  mov     [rsp+arg_8], rsi
0x18000cd6a  push    rdi
0x18000cd6b  sub     rsp, 20h
0x18000cd6f  mov     rsi, rdx
0x18000cd72  mov     rdi, rcx
0x18000cd75  mov     edx, 0A0h; uBytes
0x18000cd7a  xor     ecx, ecx; uFlags
0x18000cd7c  call    cs:__imp_LocalAlloc
0x18000cd82  mov     rbx, rax
0x18000cd85  test    rax, rax
0x18000cd88  jz      short loc_18000CDE5
0x18000cd8a  mov     r8, rsi; struct CPortMessage *
0x18000cd8d  mov     rdx, rdi; struct CAPIDispatcher *
0x18000cd90  mov     rcx, rax; this
0x18000cd93  call    ??0CAPIRequest@@QEAA@PEAVCAPIDispatcher@@AEBVCPortMessage@@@Z; CAPIRequest::CAPIRequest(CAPIDispatcher *,CPortMessage const &)
0x18000cd98  lea     rcx, ??_7CThemeManagerAPIRequest@@6BCQueueElement@@@; const CThemeManagerAPIRequest::`vftable'{for `CQueueElement'}
0x18000cd9f  mov     qword ptr [rbx+90h], 0
0x18000cdaa  mov     [rbx], rcx
0x18000cdad  lea     rax, ??_7CThemeManagerAPIRequest@@6BCPortMessage@@@; const CThemeManagerAPIRequest::`vftable'{for `CPortMessage'}
0x18000cdb4  mov     rcx, rdi; this
0x18000cdb7  mov     [rbx+10h], rax
0x18000cdbb  mov     rdx, rbx; struct CAPIRequest *
0x18000cdbe  mov     qword ptr [rbx+98h], 0
0x18000cdc9  call    ?Execute@CAPIDispatcher@@IEAAJPEAVCAPIRequest@@@Z; CAPIDispatcher::Execute(CAPIRequest *)
0x18000cdce  mov     rcx, [rbx]
0x18000cdd1  mov     edi, eax
0x18000cdd3  mov     edx, 1
0x18000cdd8  mov     rax, [rcx]
0x18000cddb  mov     rcx, rbx
0x18000cdde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cde3  jmp     short loc_18000CDEA
0x18000cde5  mov     edi, 0C0000017h
0x18000cdea  mov     rbx, [rsp+28h+arg_0]
0x18000cdef  mov     eax, edi
0x18000cdf1  mov     rsi, [rsp+28h+arg_8]
0x18000cdf6  add     rsp, 20h
0x18000cdfa  pop     rdi
0x18000cdfb  retn
```
