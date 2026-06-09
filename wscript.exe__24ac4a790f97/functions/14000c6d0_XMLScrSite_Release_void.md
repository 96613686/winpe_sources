# XMLScrSite::Release(void)

- ea: `0x14000c6d0`
- end: `0x14000c715`
- name: `?Release@XMLScrSite@@UEAAKXZ`
- size: `69`
- prototype: `unsigned int __fastcall(XMLScrSite *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x14000c720`
- `0x14000c730`

## callees

- `0x140001048`
- `0x14000c6d0`

## pseudocode

```c
__int64 __fastcall XMLScrSite::Release(XMLScrSite *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 6);
  if ( !v1 && this )
  {
    *(_QWORD *)this = &XMLScrSite::`vftable'{for `IScriptletSite'};
    *((_QWORD *)this + 1) = &XMLScrSite::`vftable'{for `IScriptletSitePoll'};
    *((_QWORD *)this + 2) = &XMLScrSite::`vftable'{for `IScriptletSiteWSH'};
    operator delete(this);
  }
  return v1;
}

```

## disassembly

```asm
0x14000c6d0  push    rbx
0x14000c6d2  sub     rsp, 20h
0x14000c6d6  or      ebx, 0FFFFFFFFh
0x14000c6d9  lock xadd [rcx+18h], ebx
0x14000c6de  sub     ebx, 1
0x14000c6e1  jnz     short loc_14000C70D
0x14000c6e3  test    rcx, rcx
0x14000c6e6  jz      short loc_14000C70D
0x14000c6e8  lea     rax, ??_7XMLScrSite@@6BIScriptletSite@@@; const XMLScrSite::`vftable'{for `IScriptletSite'}
0x14000c6ef  mov     [rcx], rax
0x14000c6f2  lea     rax, ??_7XMLScrSite@@6BIScriptletSitePoll@@@; const XMLScrSite::`vftable'{for `IScriptletSitePoll'}
0x14000c6f9  mov     [rcx+8], rax
0x14000c6fd  lea     rax, ??_7XMLScrSite@@6BIScriptletSiteWSH@@@; const XMLScrSite::`vftable'{for `IScriptletSiteWSH'}
0x14000c704  mov     [rcx+10h], rax
0x14000c708  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000c70d  mov     eax, ebx
0x14000c70f  add     rsp, 20h
0x14000c713  pop     rbx
0x14000c714  retn
```
