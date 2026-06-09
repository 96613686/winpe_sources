# DataStoreClient::GetSystemInfo(ushort *)

- ea: `0x180054770`
- end: `0x1800547ea`
- name: `?GetSystemInfo@DataStoreClient@@UEBAJPEAG@Z`
- size: `122`
- prototype: `__int64 __fastcall(DataStoreClient *__hidden this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003d140`
- `0x180043eec`

## callees

- `0x18002cca4`
- `0x180042a80`
- `0x180054770`
- `0x180058010`

## string_xrefs

- `0x1800547b3`: `GetSystemInfo() is called on a machine that doesn't support IIASDataStoreComServer2`

## pseudocode

```c
__int64 __fastcall DataStoreClient::GetSystemInfo(DataStoreClient *this, unsigned __int16 *a2)
{
  __int64 v2; // rcx
  unsigned int v3; // ebx

  v2 = *((_QWORD *)this + 8);
  if ( v2 )
  {
    return (*(unsigned int (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v2 + 88LL))(v2, a2);
  }
  else
  {
    v3 = -2147467262;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("GetSystemInfo() is called on a machine that doesn't support IIASDataStoreComServer2");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_bc84e2600b1038389a22987ce46afadc_Traceguids, "NPSDS");
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180054770  push    rbx
0x180054772  sub     rsp, 20h
0x180054776  mov     rcx, [rcx+40h]
0x18005477a  test    rcx, rcx
0x18005477d  jz      short loc_18005478F
0x18005477f  mov     rax, [rcx]
0x180054782  mov     rax, [rax+58h]
0x180054786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005478b  mov     ebx, eax
0x18005478d  jmp     short loc_1800547E2
0x18005478f  mov     rax, cs:WPP_GLOBAL_Control
0x180054796  lea     rcx, WPP_GLOBAL_Control
0x18005479d  mov     ebx, 80004002h
0x1800547a2  cmp     rax, rcx
0x1800547a5  jz      short loc_1800547E2
0x1800547a7  cmp     byte ptr [rax+19h], 2
0x1800547ab  jb      short loc_1800547E2
0x1800547ad  test    byte ptr [rax+1Ch], 10h
0x1800547b1  jz      short loc_1800547E2
0x1800547b3  lea     rcx, aGetsysteminfoI; "GetSystemInfo() is called on a machine "...
0x1800547ba  call    WppDbgPrint
0x1800547bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800547c6  lea     r9, aNpsds; "NPSDS"
0x1800547cd  mov     edx, 0Fh
0x1800547d2  lea     r8, WPP_bc84e2600b1038389a22987ce46afadc_Traceguids
0x1800547d9  mov     rcx, [rcx+10h]
0x1800547dd  call    WPP_SF_s
0x1800547e2  mov     eax, ebx
0x1800547e4  add     rsp, 20h
0x1800547e8  pop     rbx
0x1800547e9  retn
```
