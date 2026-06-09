# StartList::ClearSessionSecureConfiguration(ATL::CRegKey &)

- ea: `0x14001443c`
- end: `0x14001448a`
- name: `?ClearSessionSecureConfiguration@StartList@@AEBAXAEAVCRegKey@ATL@@@Z`
- size: `78`
- prototype: `void(StartList *__hidden this, struct ATL::CRegKey *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140015fb8`

## callees

- `0x14000f5f4`
- `0x14001443c`
- `0x14001827c`

## string_xrefs

- `0x14001444a`: `SecureConfiguration`

## pseudocode

```c
void __fastcall StartList::ClearSessionSecureConfiguration(StartList *this, HKEY *a2)
{
  unsigned int v2; // eax
  __int64 v3; // r8

  v2 = ATL::CRegKey::SetStringValue(a2, L"SecureConfiguration", (const BYTE *)&qword_14002C590);
  if ( v2 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, v3, v2);
}

```

## disassembly

```asm
0x14001443c  sub     rsp, 28h
0x140014440  mov     rcx, rdx; this
0x140014443  lea     r8, qword_14002C590; unsigned __int16 *
0x14001444a  lea     rdx, ?c_secureConfiguration@StartList@@0QBGB; "SecureConfiguration"
0x140014451  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x140014456  test    eax, eax
0x140014458  jz      short loc_140014484
0x14001445a  mov     rcx, cs:WPP_GLOBAL_Control
0x140014461  lea     rdx, WPP_GLOBAL_Control
0x140014468  cmp     rcx, rdx
0x14001446b  jz      short loc_140014484
0x14001446d  test    byte ptr [rcx+1Ch], 8
0x140014471  jz      short loc_140014484
0x140014473  mov     rcx, [rcx+10h]
0x140014477  mov     edx, 1Dh
0x14001447c  mov     r9d, eax
0x14001447f  call    WPP_SF_d
0x140014484  add     rsp, 28h
0x140014488  retn
```
