# CWSHRemote::FindConnectionPoint(_GUID const &,IConnectionPoint * *)

- ea: `0x140002640`
- end: `0x1400026e1`
- name: `?FindConnectionPoint@CWSHRemote@@UEAAJAEBU_GUID@@PEAPEAUIConnectionPoint@@@Z`
- size: `161`
- prototype: `__int64 __fastcall(CWSHRemote *__hidden this, const struct _GUID *, struct IConnectionPoint **)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x140002640`
- `0x140018010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002669`
- `KERNEL32!GetCurrentThreadId` at `0x140002669`

## pseudocode

```c
__int64 __fastcall CWSHRemote::FindConnectionPoint(
        CWSHRemote *this,
        const struct _GUID *a2,
        struct IConnectionPoint **a3)
{
  char *v7; // rdi

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = (char *)this - 16;
  if ( GetCurrentThreadId() != *((_DWORD *)this + 6) )
    return 2147549183LL;
  if ( (*(_QWORD *)&IID_IDispatch.Data1 != *(_QWORD *)&a2->Data1
     || *(_QWORD *)IID_IDispatch.Data4 != *(_QWORD *)a2->Data4)
    && (*(_QWORD *)&DIID_IWSHRemoteEvents.Data1 != *(_QWORD *)&a2->Data1
     || *(_QWORD *)DIID_IWSHRemoteEvents.Data4 != *(_QWORD *)a2->Data4) )
  {
    return 2147746304LL;
  }
  *a3 = (struct IConnectionPoint *)(((unsigned __int64)this + 8)
                                  & ((unsigned __int128)-(__int128)(unsigned __int64)v7 >> 64));
  (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))(v7);
  return 0;
}

```

## disassembly

```asm
0x140002640  push    rbx
0x140002642  push    rbp
0x140002643  push    rsi
0x140002644  push    rdi
0x140002645  sub     rsp, 28h
0x140002649  mov     rsi, r8
0x14000264c  mov     rbx, rdx
0x14000264f  mov     rbp, rcx
0x140002652  test    r8, r8
0x140002655  jnz     short loc_14000265E
0x140002657  mov     eax, 80004003h
0x14000265c  jmp     short loc_1400026D8
0x14000265e  mov     qword ptr [r8], 0
0x140002665  lea     rdi, [rcx-10h]
0x140002669  call    cs:__imp_GetCurrentThreadId
0x14000266f  cmp     eax, [rdi+28h]
0x140002672  jz      short loc_14000267B
0x140002674  mov     eax, 8000FFFFh
0x140002679  jmp     short loc_1400026D8
0x14000267b  mov     rax, qword ptr cs:IID_IDispatch.Data1
0x140002682  cmp     rax, [rbx]
0x140002685  jnz     short loc_140002694
0x140002687  mov     rax, qword ptr cs:IID_IDispatch.Data4
0x14000268e  cmp     rax, [rbx+8]
0x140002692  jz      short loc_1400026AD
0x140002694  mov     rax, qword ptr cs:DIID_IWSHRemoteEvents.Data1
0x14000269b  cmp     rax, [rbx]
0x14000269e  jnz     short loc_1400026D3
0x1400026a0  mov     rax, qword ptr cs:DIID_IWSHRemoteEvents.Data4
0x1400026a7  cmp     rax, [rbx+8]
0x1400026ab  jnz     short loc_1400026D3
0x1400026ad  lea     r8, [rbp+8]
0x1400026b1  mov     rax, rdi
0x1400026b4  neg     rax
0x1400026b7  mov     rcx, rdi
0x1400026ba  sbb     rdx, rdx
0x1400026bd  and     rdx, r8
0x1400026c0  mov     [rsi], rdx
0x1400026c3  mov     rax, [rdi]
0x1400026c6  mov     rax, [rax+8]
0x1400026ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400026cf  xor     eax, eax
0x1400026d1  jmp     short loc_1400026D8
0x1400026d3  mov     eax, 80040200h
0x1400026d8  add     rsp, 28h
0x1400026dc  pop     rdi
0x1400026dd  pop     rsi
0x1400026de  pop     rbp
0x1400026df  pop     rbx
0x1400026e0  retn
```
