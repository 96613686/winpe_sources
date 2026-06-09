# WdsDiagInitialize(void)

- ea: `0x180001050`
- end: `0x1800010e6`
- name: `?WdsDiagInitialize@@YAKXZ`
- size: `150`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001050`
- `0x180001240`
- `0x180001560`

## import_xrefs

- `ADVAPI32!EventRegister` at `0x180001079`
- `ADVAPI32!EventRegister` at `0x180001079`

## string_xrefs

- `0x180001085`: `onecore\base\eco\wds\wdslib\common\src\eventlog2.cpp`

## pseudocode

```c
__int64 __fastcall WdsDiagInitialize(__int64 a1, __int64 a2)
{
  ULONG v2; // ebx
  const char *v3; // rdx
  unsigned int v4; // eax
  int v5; // ecx
  const char *v6; // rdx

  if ( dword_180005668 )
  {
    v2 = 1247;
  }
  else
  {
    v2 = EventRegister(&MICROSOFT_WINDOWS_DEPLOYMENT_SERVICES_DIAGNOSTICS, 0, 0, &RegHandle);
    v4 = ElValidateWin32(v2, v3, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\eventlog2.cpp", 0x66u);
    v5 = dword_180005668;
    a2 = 1;
    if ( !v4 )
      v5 = 1;
    dword_180005668 = v5;
  }
  if ( !ElValidateWin32(v2, (const char *)a2, "base\\eco\\wds\\wdsdiag\\src\\wdsdiag.cpp", 0x54u) )
  {
    v2 = WdsDiagEnableAll();
    ElValidateWin32(v2, v6, "base\\eco\\wds\\wdsdiag\\src\\wdsdiag.cpp", 0x5Au);
  }
  return v2;
}

```

## disassembly

```asm
0x180001050  push    rbx
0x180001052  sub     rsp, 20h
0x180001056  cmp     cs:dword_180005668, 0
0x18000105d  jz      short loc_180001066
0x18000105f  mov     ebx, 4DFh
0x180001064  jmp     short loc_1800010AB
0x180001066  lea     r9, RegHandle; RegHandle
0x18000106d  xor     r8d, r8d; CallbackContext
0x180001070  xor     edx, edx; EnableCallback
0x180001072  lea     rcx, MICROSOFT_WINDOWS_DEPLOYMENT_SERVICES_DIAGNOSTICS; ProviderId
0x180001079  call    cs:__imp_EventRegister
0x18000107f  mov     r9d, 66h ; 'f'; unsigned int
0x180001085  lea     r8, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18000108c  mov     ecx, eax; unsigned int
0x18000108e  mov     ebx, eax
0x180001090  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001095  mov     ecx, cs:dword_180005668
0x18000109b  test    eax, eax
0x18000109d  mov     edx, 1; char *
0x1800010a2  cmovz   ecx, edx
0x1800010a5  mov     cs:dword_180005668, ecx
0x1800010ab  mov     r9d, 54h ; 'T'; unsigned int
0x1800010b1  lea     r8, aBaseEcoWdsWdsd; "base\\eco\\wds\\wdsdiag\\src\\wdsdiag.c"...
0x1800010b8  mov     ecx, ebx; unsigned int
0x1800010ba  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800010bf  test    eax, eax
0x1800010c1  jnz     short loc_1800010DE
0x1800010c3  call    ?WdsDiagEnableAll@@YAKXZ; WdsDiagEnableAll(void)
0x1800010c8  mov     r9d, 5Ah ; 'Z'; unsigned int
0x1800010ce  lea     r8, aBaseEcoWdsWdsd; "base\\eco\\wds\\wdsdiag\\src\\wdsdiag.c"...
0x1800010d5  mov     ecx, eax; unsigned int
0x1800010d7  mov     ebx, eax
0x1800010d9  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800010de  mov     eax, ebx
0x1800010e0  add     rsp, 20h
0x1800010e4  pop     rbx
0x1800010e5  retn
```
