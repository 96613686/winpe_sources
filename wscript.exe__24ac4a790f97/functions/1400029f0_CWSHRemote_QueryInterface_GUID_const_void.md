# CWSHRemote::QueryInterface(_GUID const &,void * *)

- ea: `0x1400029f0`
- end: `0x140002aec`
- name: `?QueryInterface@CWSHRemote@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `252`
- prototype: `__int64 __fastcall(CWSHRemote *__hidden this, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140002b00`
- `0x140002b10`
- `0x140002b20`

## callees

- `0x1400029f0`
- `0x140018010`

## pseudocode

```c
__int64 __fastcall CWSHRemote::QueryInterface(CWSHRemote *this, const struct _GUID *a2, CWSHRemote **a3)
{
  unsigned __int64 v5; // rcx
  CWSHRemote *v6; // rax

  if ( !a3 )
    return 2147500035LL;
  if ( *(_QWORD *)&IID_IUnknown.Data1 == *(_QWORD *)&a2->Data1 && *(_QWORD *)IID_IUnknown.Data4 == *(_QWORD *)a2->Data4
    || *(_QWORD *)&IID_IDispatch.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)IID_IDispatch.Data4 == *(_QWORD *)a2->Data4 )
  {
    goto LABEL_19;
  }
  if ( *(_QWORD *)&IID_IProvideClassInfo.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)IID_IProvideClassInfo.Data4 == *(_QWORD *)a2->Data4 )
  {
    v5 = (unsigned __int64)this + 8;
LABEL_16:
    v6 = (CWSHRemote *)(v5 & -(__int64)(this != 0));
LABEL_20:
    *a3 = v6;
    (*(void (__fastcall **)(CWSHRemote *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
  if ( *(_QWORD *)&IID_IConnectionPointContainer.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)IID_IConnectionPointContainer.Data4 == *(_QWORD *)a2->Data4 )
  {
    v5 = (unsigned __int64)this + 16;
    goto LABEL_16;
  }
  if ( *(_QWORD *)&IID_IConnectionPoint.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)IID_IConnectionPoint.Data4 == *(_QWORD *)a2->Data4 )
  {
    v5 = (unsigned __int64)this + 24;
    goto LABEL_16;
  }
  if ( *(_QWORD *)&IID_IWSHRemote.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)IID_IWSHRemote.Data4 == *(_QWORD *)a2->Data4 )
  {
LABEL_19:
    v6 = this;
    goto LABEL_20;
  }
  *a3 = 0;
  return 2147500034LL;
}

```

## disassembly

```asm
0x1400029f0  sub     rsp, 28h
0x1400029f4  mov     r9, rcx
0x1400029f7  test    r8, r8
0x1400029fa  jnz     short loc_140002A06
0x1400029fc  mov     eax, 80004003h
0x140002a01  jmp     loc_140002AE7
0x140002a06  mov     rax, qword ptr cs:IID_IUnknown.Data1
0x140002a0d  cmp     rax, [rdx]
0x140002a10  jnz     short loc_140002A23
0x140002a12  mov     rax, qword ptr cs:IID_IUnknown.Data4
0x140002a19  cmp     rax, [rdx+8]
0x140002a1d  jz      loc_140002AC2
0x140002a23  mov     rax, qword ptr cs:IID_IDispatch.Data1
0x140002a2a  cmp     rax, [rdx]
0x140002a2d  jnz     short loc_140002A40
0x140002a2f  mov     rax, qword ptr cs:IID_IDispatch.Data4
0x140002a36  cmp     rax, [rdx+8]
0x140002a3a  jz      loc_140002AC2
0x140002a40  mov     rax, qword ptr cs:IID_IProvideClassInfo.Data1
0x140002a47  cmp     rax, [rdx]
0x140002a4a  jnz     short loc_140002A5F
0x140002a4c  mov     rax, qword ptr cs:IID_IProvideClassInfo.Data4
0x140002a53  cmp     rax, [rdx+8]
0x140002a57  jnz     short loc_140002A5F
0x140002a59  add     rcx, 8
0x140002a5d  jmp     short loc_140002A9B
0x140002a5f  mov     rax, qword ptr cs:IID_IConnectionPointContainer.Data1
0x140002a66  cmp     rax, [rdx]
0x140002a69  jnz     short loc_140002A7E
0x140002a6b  mov     rax, qword ptr cs:IID_IConnectionPointContainer.Data4
0x140002a72  cmp     rax, [rdx+8]
0x140002a76  jnz     short loc_140002A7E
0x140002a78  add     rcx, 10h
0x140002a7c  jmp     short loc_140002A9B
0x140002a7e  mov     rax, qword ptr cs:IID_IConnectionPoint.Data1
0x140002a85  cmp     rax, [rdx]
0x140002a88  jnz     short loc_140002AA9
0x140002a8a  mov     rax, qword ptr cs:IID_IConnectionPoint.Data4
0x140002a91  cmp     rax, [rdx+8]
0x140002a95  jnz     short loc_140002AA9
0x140002a97  add     rcx, 18h
0x140002a9b  mov     rax, r9
0x140002a9e  neg     rax
0x140002aa1  sbb     rax, rax
0x140002aa4  and     rax, rcx
0x140002aa7  jmp     short loc_140002AC5
0x140002aa9  mov     rax, qword ptr cs:IID_IWSHRemote.Data1
0x140002ab0  cmp     rax, [rdx]
0x140002ab3  jnz     short loc_140002ADB
0x140002ab5  mov     rax, qword ptr cs:IID_IWSHRemote.Data4
0x140002abc  cmp     rax, [rdx+8]
0x140002ac0  jnz     short loc_140002ADB
0x140002ac2  mov     rax, r9
0x140002ac5  mov     [r8], rax
0x140002ac8  mov     rcx, r9
0x140002acb  mov     rax, [r9]
0x140002ace  mov     rax, [rax+8]
0x140002ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002ad7  xor     eax, eax
0x140002ad9  jmp     short loc_140002AE7
0x140002adb  mov     qword ptr [r8], 0
0x140002ae2  mov     eax, 80004002h
0x140002ae7  add     rsp, 28h
0x140002aeb  retn
```
