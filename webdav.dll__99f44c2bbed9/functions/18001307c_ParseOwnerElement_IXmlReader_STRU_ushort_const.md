# ParseOwnerElement(IXmlReader *,STRU *,ushort const *)

- ea: `0x18001307c`
- end: `0x180013176`
- name: `?ParseOwnerElement@@YAJPEAUIXmlReader@@PEAVSTRU@@PEBG@Z`
- size: `250`
- prototype: `int __fastcall(struct IXmlReader *, struct STRU *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180012c54`

## callees

- `0x18001307c`
- `0x18001317c`
- `0x18001e104`
- `0x180023010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800130a6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800130a6`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180013122`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180013160`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180013122`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180013160`

## pseudocode

```c
int __fastcall ParseOwnerElement(struct IXmlReader *a1, struct STRU *a2, const unsigned __int16 *a3)
{
  int result; // eax
  int v7; // edx
  struct IXmlReaderVtbl *lpVtbl; // rax
  const unsigned __int16 *v9; // [rsp+20h] [rbp-18h] BYREF
  int v10; // [rsp+58h] [rbp+20h] BYREF

  v10 = 0;
  result = STRU::Copy(a2, L"<D:owner>");
  if ( result >= 0 )
  {
    while ( 1 )
    {
      result = ((__int64 (__fastcall *)(struct IXmlReader *, int *))a1->lpVtbl->Read)(a1, &v10);
      if ( result == 1 )
        return STRU::Append(a2, L"</D:owner>");
      if ( result < 0 )
        return result;
      v7 = v10;
      if ( v10 == 1 )
        break;
      switch ( v10 )
      {
        case 3:
          goto LABEL_8;
        case 4:
          result = XmlAppendCData(a1, a2);
LABEL_12:
          if ( result < 0 )
            return result;
          v7 = v10;
          break;
        case 13:
LABEL_8:
          lpVtbl = a1->lpVtbl;
          v9 = 0;
          result = ((__int64 (__fastcall *)(struct IXmlReader *, const unsigned __int16 **, _QWORD))lpVtbl->GetValue)(
                     a1,
                     &v9,
                     0);
          if ( result < 0 )
            return result;
          result = STRU::Append(a2, v9);
          goto LABEL_12;
      }
      if ( v7 == 15 )
        return STRU::Append(a2, L"</D:owner>");
    }
    result = ParseOwnerSubElement(a1, a3, a2);
    goto LABEL_12;
  }
  return result;
}

```

## disassembly

```asm
0x18001307c  mov     [rsp+arg_0], rbx
0x180013081  mov     [rsp+arg_8], rsi
0x180013086  push    rdi
0x180013087  sub     rsp, 30h
0x18001308b  mov     rbx, rdx
0x18001308e  mov     [rsp+38h+arg_18], 0
0x180013096  mov     rdi, rcx
0x180013099  lea     rdx, aDOwner_0; "<D:owner>"
0x1800130a0  mov     rcx, rbx
0x1800130a3  mov     rsi, r8
0x1800130a6  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800130ac  test    eax, eax
0x1800130ae  js      loc_180013166
0x1800130b4  mov     rax, [rdi]
0x1800130b7  lea     rdx, [rsp+38h+arg_18]
0x1800130bc  mov     rcx, rdi
0x1800130bf  mov     rax, [rax+30h]
0x1800130c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130c8  cmp     eax, 1
0x1800130cb  jz      loc_180013156
0x1800130d1  test    eax, eax
0x1800130d3  js      loc_180013166
0x1800130d9  mov     edx, [rsp+38h+arg_18]
0x1800130dd  mov     ecx, edx
0x1800130df  sub     ecx, 1
0x1800130e2  jz      short loc_180013137
0x1800130e4  sub     ecx, 2
0x1800130e7  jz      short loc_1800130F3
0x1800130e9  sub     ecx, 1
0x1800130ec  jz      short loc_18001312A
0x1800130ee  cmp     ecx, 9
0x1800130f1  jnz     short loc_18001314D
0x1800130f3  mov     rax, [rdi]
0x1800130f6  lea     rdx, [rsp+38h+var_18]
0x1800130fb  xor     r8d, r8d
0x1800130fe  mov     [rsp+38h+var_18], 0
0x180013107  mov     rcx, rdi
0x18001310a  mov     rax, [rax+80h]
0x180013111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013116  test    eax, eax
0x180013118  js      short loc_180013166
0x18001311a  mov     rdx, [rsp+38h+var_18]
0x18001311f  mov     rcx, rbx
0x180013122  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180013128  jmp     short loc_180013145
0x18001312a  mov     rdx, rbx; struct STRU *
0x18001312d  mov     rcx, rdi; struct IXmlReader *
0x180013130  call    ?XmlAppendCData@@YAJPEAUIXmlReader@@PEAVSTRU@@@Z; XmlAppendCData(IXmlReader *,STRU *)
0x180013135  jmp     short loc_180013145
0x180013137  mov     r8, rbx; struct STRU *
0x18001313a  mov     rdx, rsi; unsigned __int16 *
0x18001313d  mov     rcx, rdi; struct IXmlReader *
0x180013140  call    ?ParseOwnerSubElement@@YAJPEAUIXmlReader@@PEBGPEAVSTRU@@@Z; ParseOwnerSubElement(IXmlReader *,ushort const *,STRU *)
0x180013145  test    eax, eax
0x180013147  js      short loc_180013166
0x180013149  mov     edx, [rsp+38h+arg_18]
0x18001314d  cmp     edx, 0Fh
0x180013150  jnz     loc_1800130B4
0x180013156  lea     rdx, aDOwner; "</D:owner>"
0x18001315d  mov     rcx, rbx
0x180013160  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180013166  mov     rbx, [rsp+38h+arg_0]
0x18001316b  mov     rsi, [rsp+38h+arg_8]
0x180013170  add     rsp, 30h
0x180013174  pop     rdi
0x180013175  retn
```
