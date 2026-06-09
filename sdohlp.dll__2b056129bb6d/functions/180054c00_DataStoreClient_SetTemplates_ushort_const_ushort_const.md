# DataStoreClient::SetTemplates(ushort const *,ushort const *)

- ea: `0x180054c00`
- end: `0x180054c7a`
- name: `?SetTemplates@DataStoreClient@@UEAAJPEBG0@Z`
- size: `122`
- prototype: `__int64 __fastcall(DataStoreClient *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18002cca4`
- `0x180042a80`
- `0x180054c00`
- `0x180058010`

## string_xrefs

- `0x180054c43`: `SetTemplates() is called on a machine that doesn't support templates`

## pseudocode

```c
__int64 __fastcall DataStoreClient::SetTemplates(
        DataStoreClient *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v3; // rcx
  unsigned int v4; // ebx

  v3 = *((_QWORD *)this + 8);
  if ( v3 )
  {
    return (*(unsigned int (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 *))(*(_QWORD *)v3 + 72LL))(
             v3,
             a2,
             a3);
  }
  else
  {
    v4 = -2147467262;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("SetTemplates() is called on a machine that doesn't support templates");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_bc84e2600b1038389a22987ce46afadc_Traceguids, "NPSDS");
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180054c00  push    rbx
0x180054c02  sub     rsp, 20h
0x180054c06  mov     rcx, [rcx+40h]
0x180054c0a  test    rcx, rcx
0x180054c0d  jz      short loc_180054C1F
0x180054c0f  mov     rax, [rcx]
0x180054c12  mov     rax, [rax+48h]
0x180054c16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c1b  mov     ebx, eax
0x180054c1d  jmp     short loc_180054C72
0x180054c1f  mov     rax, cs:WPP_GLOBAL_Control
0x180054c26  lea     rcx, WPP_GLOBAL_Control
0x180054c2d  mov     ebx, 80004002h
0x180054c32  cmp     rax, rcx
0x180054c35  jz      short loc_180054C72
0x180054c37  cmp     byte ptr [rax+19h], 2
0x180054c3b  jb      short loc_180054C72
0x180054c3d  test    byte ptr [rax+1Ch], 10h
0x180054c41  jz      short loc_180054C72
0x180054c43  lea     rcx, aSettemplatesIs; "SetTemplates() is called on a machine t"...
0x180054c4a  call    WppDbgPrint
0x180054c4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180054c56  lea     r9, aNpsds; "NPSDS"
0x180054c5d  mov     edx, 0Dh
0x180054c62  lea     r8, WPP_bc84e2600b1038389a22987ce46afadc_Traceguids
0x180054c69  mov     rcx, [rcx+10h]
0x180054c6d  call    WPP_SF_s
0x180054c72  mov     eax, ebx
0x180054c74  add     rsp, 20h
0x180054c78  pop     rbx
0x180054c79  retn
```
