# CSecurityAttribute::Clean(void)

- ea: `0x140011d18`
- end: `0x140011dc5`
- name: `?Clean@CSecurityAttribute@@AEAAXXZ`
- size: `173`
- prototype: `void __fastcall(CSecurityAttribute *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140011dcc`
- `0x140012818`

## callees

- `0x140001258`
- `0x140011d18`
- `0x140013490`

## import_xrefs

- `ADVAPI32!FreeSid` at `0x140011db1`
- `ADVAPI32!FreeSid` at `0x140011db1`

## string_xrefs

- `0x140011d2c`: `Security attribute 0X%x has been released already`
- `0x140011d38`: `CSecurityAttribute::Clean`

## pseudocode

```c
void __fastcall CSecurityAttribute::Clean(CSecurityAttribute *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx

  v2 = *(void **)this;
  if ( v2 )
  {
    operator delete(v2);
    v3 = (void *)*((_QWORD *)this + 5);
    *(_QWORD *)this = 0;
    if ( v3 )
    {
      operator delete(v3);
      *((_QWORD *)this + 5) = 0;
    }
    v4 = (void *)*((_QWORD *)this + 4);
    if ( v4 )
    {
      operator delete(v4);
      *((_QWORD *)this + 4) = 0;
    }
    v5 = (void *)*((_QWORD *)this + 2);
    if ( v5 )
    {
      operator delete(v5);
      *((_QWORD *)this + 2) = 0;
    }
    v6 = (void *)*((_QWORD *)this + 3);
    if ( v6 )
    {
      operator delete(v6);
      *((_QWORD *)this + 3) = 0;
    }
    FreeSid(*((PSID *)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
  else
  {
    WusaLogDebugEventA(L"CSecurityAttribute::Clean", 333, "Security attribute 0X%x has been released already", 0);
  }
}

```

## disassembly

```asm
0x140011d18  push    rbx
0x140011d1a  sub     rsp, 20h
0x140011d1e  mov     rbx, rcx
0x140011d21  mov     rcx, [rcx]; Block
0x140011d24  test    rcx, rcx
0x140011d27  jnz     short loc_140011D49
0x140011d29  xor     r9d, r9d
0x140011d2c  lea     r8, aSecurityAttrib; "Security attribute 0X%x has been releas"...
0x140011d33  mov     edx, 14Dh
0x140011d38  lea     rcx, aCsecurityattri_4; "CSecurityAttribute::Clean"
0x140011d3f  add     rsp, 20h
0x140011d43  pop     rbx
0x140011d44  jmp     WusaLogDebugEventA
0x140011d49  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140011d4e  mov     rcx, [rbx+28h]; Block
0x140011d52  mov     qword ptr [rbx], 0
0x140011d59  test    rcx, rcx
0x140011d5c  jz      short loc_140011D6B
0x140011d5e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140011d63  mov     qword ptr [rbx+28h], 0
0x140011d6b  mov     rcx, [rbx+20h]; Block
0x140011d6f  test    rcx, rcx
0x140011d72  jz      short loc_140011D81
0x140011d74  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140011d79  mov     qword ptr [rbx+20h], 0
0x140011d81  mov     rcx, [rbx+10h]; Block
0x140011d85  test    rcx, rcx
0x140011d88  jz      short loc_140011D97
0x140011d8a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140011d8f  mov     qword ptr [rbx+10h], 0
0x140011d97  mov     rcx, [rbx+18h]; Block
0x140011d9b  test    rcx, rcx
0x140011d9e  jz      short loc_140011DAD
0x140011da0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140011da5  mov     qword ptr [rbx+18h], 0
0x140011dad  mov     rcx, [rbx+8]; pSid
0x140011db1  call    cs:__imp_FreeSid
0x140011db7  mov     qword ptr [rbx+8], 0
0x140011dbf  add     rsp, 20h
0x140011dc3  pop     rbx
0x140011dc4  retn
```
