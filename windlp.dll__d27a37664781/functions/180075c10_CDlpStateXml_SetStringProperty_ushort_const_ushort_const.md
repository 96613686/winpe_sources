# CDlpStateXml::SetStringProperty(ushort const *,ushort const *)

- ea: `0x180075c10`
- end: `0x180075ce9`
- name: `?SetStringProperty@CDlpStateXml@@UEAAJPEBG0@Z`
- size: `217`
- prototype: `__int64 __fastcall(CDlpStateXml *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000aba4`
- `0x18001fd60`
- `0x180068488`
- `0x180075c10`

## import_xrefs

- `UNATTEND!UnattendFreeNode` at `0x180075c95`
- `UNATTEND!UnattendFreeNode` at `0x180075cd1`
- `UNATTEND!UnattendFreeNode` at `0x180075c95`
- `UNATTEND!UnattendFreeNode` at `0x180075cd1`
- `UNATTEND!UnattendCtxBeginModify` at `0x180075c64`
- `UNATTEND!UnattendCtxBeginModify` at `0x180075c64`
- `UNATTEND!UnattendCtxCommitModify` at `0x180075cb9`
- `UNATTEND!UnattendCtxCommitModify` at `0x180075cb9`
- `UNATTEND!UnattendCtxSetStringByNode` at `0x180075c84`
- `UNATTEND!UnattendCtxSetStringByNode` at `0x180075c84`

## pseudocode

```c
__int64 __fastcall CDlpStateXml::SetStringProperty(
        CDlpStateXml *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rcx
  unsigned int v7; // ebx
  int v8; // eax
  __int64 v9; // rcx
  __int128 v11; // [rsp+30h] [rbp-58h] BYREF
  __int128 v12; // [rsp+40h] [rbp-48h]
  __int64 v13; // [rsp+50h] [rbp-38h]

  v13 = 0;
  v11 = 0;
  v12 = 0;
  if ( !a2 || !a3 )
  {
    v6 = 2147942487LL;
    v7 = -2147024809;
LABEL_10:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    goto LABEL_11;
  }
  v8 = CDlpStateXml::OpenCurrentNode((CDlpStateXml *)((char *)this - 8), (struct _UNATTEND_NODE *)&v11);
  v7 = v8;
  if ( v8 < 0 )
    goto LABEL_9;
  v8 = UnattendCtxBeginModify(*((_QWORD *)this + 15));
  v7 = v8;
  if ( v8 < 0 )
    goto LABEL_9;
  v8 = UnattendCtxSetStringByNode(*((_QWORD *)this + 15), &v11, a2, 0, a3);
  v7 = v8;
  if ( v8 < 0 )
    goto LABEL_9;
  v8 = UnattendFreeNode(&v11);
  v7 = v8;
  if ( v8 < 0
    || (v9 = *((_QWORD *)this + 15), v11 = 0, v13 = 0, v12 = 0, v8 = UnattendCtxCommitModify(v9), v7 = v8, v8 < 0) )
  {
LABEL_9:
    v6 = (unsigned int)v8;
    goto LABEL_10;
  }
LABEL_11:
  UnattendFreeNode(&v11);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  return v7;
}

```

## disassembly

```asm
0x180075c10  push    rbx
0x180075c12  push    rbp
0x180075c13  push    rsi
0x180075c14  push    rdi
0x180075c15  sub     rsp, 68h
0x180075c19  xor     eax, eax
0x180075c1b  xorps   xmm0, xmm0
0x180075c1e  mov     [rsp+88h+var_38], rax
0x180075c23  mov     rsi, r8
0x180075c26  mov     rbp, rdx
0x180075c29  mov     rdi, rcx
0x180075c2c  movups  [rsp+88h+var_58], xmm0
0x180075c31  movups  [rsp+88h+var_48], xmm0
0x180075c36  test    rdx, rdx
0x180075c39  jnz     short loc_180075C47
0x180075c3b  mov     ecx, 80070057h
0x180075c40  mov     ebx, ecx
0x180075c42  jmp     loc_180075CC7
0x180075c47  test    rsi, rsi
0x180075c4a  jz      short loc_180075C3B
0x180075c4c  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x180075c50  lea     rdx, [rsp+88h+var_58]; struct _UNATTEND_NODE *
0x180075c55  call    ?OpenCurrentNode@CDlpStateXml@@AEAAJPEAU_UNATTEND_NODE@@@Z; CDlpStateXml::OpenCurrentNode(_UNATTEND_NODE *)
0x180075c5a  mov     ebx, eax
0x180075c5c  test    eax, eax
0x180075c5e  js      short loc_180075CC5
0x180075c60  mov     rcx, [rdi+78h]
0x180075c64  call    cs:__imp_UnattendCtxBeginModify
0x180075c6a  mov     ebx, eax
0x180075c6c  test    eax, eax
0x180075c6e  js      short loc_180075CC5
0x180075c70  mov     rcx, [rdi+78h]
0x180075c74  lea     rdx, [rsp+88h+var_58]
0x180075c79  xor     r9d, r9d
0x180075c7c  mov     [rsp+88h+var_68], rsi
0x180075c81  mov     r8, rbp
0x180075c84  call    cs:__imp_UnattendCtxSetStringByNode
0x180075c8a  mov     ebx, eax
0x180075c8c  test    eax, eax
0x180075c8e  js      short loc_180075CC5
0x180075c90  lea     rcx, [rsp+88h+var_58]
0x180075c95  call    cs:__imp_UnattendFreeNode
0x180075c9b  mov     ebx, eax
0x180075c9d  test    eax, eax
0x180075c9f  js      short loc_180075CC5
0x180075ca1  mov     rcx, [rdi+78h]
0x180075ca5  xorps   xmm0, xmm0
0x180075ca8  xor     eax, eax
0x180075caa  movups  [rsp+88h+var_58], xmm0
0x180075caf  mov     [rsp+88h+var_38], rax
0x180075cb4  movups  [rsp+88h+var_48], xmm0
0x180075cb9  call    cs:__imp_UnattendCtxCommitModify
0x180075cbf  mov     ebx, eax
0x180075cc1  test    eax, eax
0x180075cc3  jns     short loc_180075CCC
0x180075cc5  mov     ecx, eax
0x180075cc7  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180075ccc  lea     rcx, [rsp+88h+var_58]
0x180075cd1  call    cs:__imp_UnattendFreeNode
0x180075cd7  mov     ecx, ebx
0x180075cd9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180075cde  mov     eax, ebx
0x180075ce0  add     rsp, 68h
0x180075ce4  pop     rdi
0x180075ce5  pop     rsi
0x180075ce6  pop     rbp
0x180075ce7  pop     rbx
0x180075ce8  retn
```
