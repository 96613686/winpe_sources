# Get_supportedlock(DAV_RESOURCE *,DAV_PROPERTY *,LIVE_ADDITIONAL_DATA *)

- ea: `0x18000ba40`
- end: `0x18000ba87`
- name: `?Get_supportedlock@@YAJPEAVDAV_RESOURCE@@PEAVDAV_PROPERTY@@PEAULIVE_ADDITIONAL_DATA@@@Z`
- size: `71`
- prototype: `__int64 __fastcall(struct DAV_RESOURCE *, struct DAV_PROPERTY *, struct LIVE_ADDITIONAL_DATA *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000ba40`
- `0x180023010`

## string_xrefs

- `0x18000ba61`: `<D:lockentry><D:lockscope><D:exclusive/></D:lockscope><D:locktype><D:write/></D:locktype></D:lockentry><D:lockentry><D:lockscope><D:shared/></D:lockscope><D:locktype><D:write/></D:locktype></D:lockentry>`
- `0x18000ba55`: `\n<D:lockentry>\n<D:lockscope><D:exclusive/></D:lockscope>\n<D:locktype><D:write/></D:locktype>\n</D:lockentry>\n<D:lockentry>\n<D:lockscope><D:shared/></D:lockscope>\n<D:locktype><D:write/></D:locktype>\n</D:lockentry>\n`

## pseudocode

```c
__int64 __fastcall Get_supportedlock(struct DAV_RESOURCE *a1, struct DAV_PROPERTY *a2, struct LIVE_ADDITIONAL_DATA *a3)
{
  unsigned int v3; // ecx
  __int64 v5; // rax
  const wchar_t *v6; // rdx

  v3 = 0;
  if ( *(_DWORD *)(*((_QWORD *)a3 + 7) + 28LL) )
  {
    v5 = *(_QWORD *)a2;
    v6 = L"<D:lockentry><D:lockscope><D:exclusive/></D:lockscope><D:locktype><D:write/></D:locktype></D:lockentry><D:locke"
          "ntry><D:lockscope><D:shared/></D:lockscope><D:locktype><D:write/></D:locktype></D:lockentry>";
    if ( (*((_BYTE *)a3 + 64) & 4) == 0 )
      v6 = L"\r\n"
            "<D:lockentry>\r\n"
            "<D:lockscope><D:exclusive/></D:lockscope>\r\n"
            "<D:locktype><D:write/></D:locktype>\r\n"
            "</D:lockentry>\r\n"
            "<D:lockentry>\r\n"
            "<D:lockscope><D:shared/></D:lockscope>\r\n"
            "<D:locktype><D:write/></D:locktype>\r\n"
            "</D:lockentry>\r\n";
    return (*(unsigned int (__fastcall **)(struct DAV_PROPERTY *, const wchar_t *, _QWORD, _QWORD))(v5 + 64))(
             a2,
             v6,
             0,
             0);
  }
  return v3;
}

```

## disassembly

```asm
0x18000ba40  sub     rsp, 38h
0x18000ba44  mov     rax, [r8+38h]
0x18000ba48  xor     ecx, ecx
0x18000ba4a  mov     r10, rdx
0x18000ba4d  cmp     [rax+1Ch], ecx
0x18000ba50  jz      short loc_18000BA80
0x18000ba52  mov     rax, [rdx]
0x18000ba55  lea     rcx, aDLockentryDLoc; "\r\n<D:lockentry>\r\n<D:lockscope><D:ex"...
0x18000ba5c  test    byte ptr [r8+40h], 4
0x18000ba61  lea     rdx, aDLockentryDLoc_0; "<D:lockentry><D:lockscope><D:exclusive/"...
0x18000ba68  cmovz   rdx, rcx
0x18000ba6c  xor     r9d, r9d
0x18000ba6f  mov     rax, [rax+40h]
0x18000ba73  xor     r8d, r8d
0x18000ba76  mov     rcx, r10
0x18000ba79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba7e  mov     ecx, eax
0x18000ba80  mov     eax, ecx
0x18000ba82  add     rsp, 38h
0x18000ba86  retn
```
