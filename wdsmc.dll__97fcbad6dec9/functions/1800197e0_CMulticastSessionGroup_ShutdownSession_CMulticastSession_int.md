# CMulticastSessionGroup::ShutdownSession(CMulticastSession *,int)

- ea: `0x1800197e0`
- end: `0x18001986e`
- name: `?ShutdownSession@CMulticastSessionGroup@@AEAAXPEAVCMulticastSession@@H@Z`
- size: `142`
- prototype: `void(CMulticastSessionGroup *__hidden this, struct CMulticastSession *, int)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x180019770`
- `0x180019a3c`
- `0x18001a514`

## callees

- `0x18000bdd4`
- `0x180017254`
- `0x180017410`
- `0x1800174cc`
- `0x1800197e0`
- `0x18001a83c`
- `0x1800227d4`

## string_xrefs

- `0x180019839`: `pSession->CanDelete()`

## pseudocode

```c
void __fastcall CMulticastSessionGroup::ShutdownSession(
        CMulticastSessionGroup *this,
        struct CMulticastSession *a2,
        int a3)
{
  int v6; // r9d

  CMulticastSession::Close(a2, a3);
  if ( a3 )
  {
    CMcCoClients::DeleteAllSessionClients(
      (CMcCoClients *)(*((_QWORD *)this + 7) + 312LL),
      _InterlockedExchangeAdd((volatile signed __int32 *)a2 + 632, 0));
    CMulticastSession::Shutdown(a2);
    if ( !(unsigned int)CMulticastSession::CanDelete(a2) )
      WdsAssert("base\\eco\\wds\\transport\\server\\mc\\mcsessiongroup.cpp", 0x1ACu, "pSession->CanDelete()", v6, 0);
    if ( a2 )
      CMulticastSession::`scalar deleting destructor'(a2);
  }
}

```

## disassembly

```asm
0x1800197e0  mov     [rsp+arg_0], rbx
0x1800197e5  mov     [rsp+arg_8], rsi
0x1800197ea  push    rdi
0x1800197eb  sub     rsp, 30h
0x1800197ef  mov     rdi, rdx
0x1800197f2  mov     rsi, rcx
0x1800197f5  mov     rcx, rdi; this
0x1800197f8  mov     edx, r8d; int
0x1800197fb  mov     ebx, r8d
0x1800197fe  call    ?Close@CMulticastSession@@QEAAKH@Z; CMulticastSession::Close(int)
0x180019803  test    ebx, ebx
0x180019805  jz      short loc_18001985E
0x180019807  xor     edx, edx
0x180019809  lock xadd [rdi+9E0h], edx; unsigned int
0x180019811  mov     rcx, [rsi+38h]
0x180019815  add     rcx, 138h; this
0x18001981c  call    ?DeleteAllSessionClients@CMcCoClients@@QEAAXK@Z; CMcCoClients::DeleteAllSessionClients(ulong)
0x180019821  mov     rcx, rdi; this
0x180019824  call    ?Shutdown@CMulticastSession@@QEAAKXZ; CMulticastSession::Shutdown(void)
0x180019829  mov     rcx, rdi; this
0x18001982c  call    ?CanDelete@CMulticastSession@@QEAAHXZ; CMulticastSession::CanDelete(void)
0x180019831  test    eax, eax
0x180019833  jnz     short loc_180019851
0x180019835  and     [rsp+38h+var_18], eax
0x180019839  lea     r8, aPsessionCandel; "pSession->CanDelete()"
0x180019840  mov     edx, 1ACh; unsigned int
0x180019845  lea     rcx, aBaseEcoWdsTran_12; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18001984c  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180019851  test    rdi, rdi
0x180019854  jz      short loc_18001985E
0x180019856  mov     rcx, rdi; this
0x180019859  call    ??_GCMulticastSession@@QEAAPEAXI@Z; CMulticastSession::`scalar deleting destructor'(uint)
0x18001985e  mov     rbx, [rsp+38h+arg_0]
0x180019863  mov     rsi, [rsp+38h+arg_8]
0x180019868  add     rsp, 30h
0x18001986c  pop     rdi
0x18001986d  retn
```
