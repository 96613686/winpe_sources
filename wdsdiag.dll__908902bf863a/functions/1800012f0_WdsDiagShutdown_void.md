# WdsDiagShutdown(void)

- ea: `0x1800012f0`
- end: `0x180001337`
- name: `?WdsDiagShutdown@@YAKXZ`
- size: `71`
- prototype: `unsigned int(void)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800012f0`
- `0x180001560`

## import_xrefs

- `ADVAPI32!EventUnregister` at `0x180001304`
- `ADVAPI32!EventUnregister` at `0x180001304`

## pseudocode

```c
__int64 __fastcall WdsDiagShutdown(__int64 a1, const char *a2)
{
  unsigned int v2; // ebx
  ULONG v3; // eax

  v2 = 0;
  if ( RegHandle )
  {
    v3 = EventUnregister(RegHandle);
    RegHandle = 0;
    v2 = v3;
  }
  dword_180005668 = 0;
  ElValidateWin32(v2, a2, "base\\eco\\wds\\wdsdiag\\src\\wdsdiag.cpp", 0x168u);
  return v2;
}

```

## disassembly

```asm
0x1800012f0  push    rbx
0x1800012f2  sub     rsp, 20h
0x1800012f6  mov     rcx, cs:RegHandle; RegHandle
0x1800012fd  xor     ebx, ebx
0x1800012ff  test    rcx, rcx
0x180001302  jz      short loc_180001314
0x180001304  call    cs:__imp_EventUnregister
0x18000130a  and     cs:RegHandle, 0
0x180001312  mov     ebx, eax
0x180001314  and     cs:dword_180005668, 0
0x18000131b  lea     r8, aBaseEcoWdsWdsd; "base\\eco\\wds\\wdsdiag\\src\\wdsdiag.c"...
0x180001322  mov     r9d, 168h; unsigned int
0x180001328  mov     ecx, ebx; unsigned int
0x18000132a  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000132f  mov     eax, ebx
0x180001331  add     rsp, 20h
0x180001335  pop     rbx
0x180001336  retn
```
