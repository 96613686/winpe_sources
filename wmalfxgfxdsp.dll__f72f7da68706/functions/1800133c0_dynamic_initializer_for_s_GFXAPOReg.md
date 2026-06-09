# _dynamic_initializer_for__s_GFXAPOReg__

- ea: `0x1800133c0`
- end: `0x180013474`
- name: `_dynamic_initializer_for__s_GFXAPOReg__`
- size: `180`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180015ea8`

## string_xrefs

- `0x1800133e7`: `Copyright Microsoft`

## pseudocode

```c
__int64 dynamic_initializer_for__s_GFXAPOReg__()
{
  __int64 result; // rax

  pProperties.clsid = CLSID_CWMAudioGFXAPO;
  memset_0(&pProperties.szFriendlyName[17], 0, 0x1DEu);
  wcscpy(pProperties.szCopyrightInfo, L"Copyright Microsoft");
  memset_0(&pProperties.szCopyrightInfo[20], 0, 0x1D8u);
  result = 1;
  pProperties.u32MaxInstances = -1;
  pProperties.u32MajorVersion = 1;
  pProperties.iidAPOInterfaceList[0] = GUID_fd7f2b29_24d0_4b5c_b177_592c39f9ca10;
  pProperties.u32MinorVersion = 1;
  pProperties.u32MinInputConnections = 1;
  pProperties.u32MaxInputConnections = 1;
  pProperties.u32MinOutputConnections = 1;
  pProperties.u32MaxOutputConnections = 1;
  pProperties.u32NumAPOInterfaces = 1;
  return result;
}

```

## disassembly

```asm
0x1800133c0  sub     rsp, 28h
0x1800133c4  movups  xmm0, xmmword ptr cs:CLSID_CWMAudioGFXAPO.Data1
0x1800133cb  xor     edx, edx; Val
0x1800133cd  lea     rcx, pProperties.szFriendlyName+22h; void *
0x1800133d4  mov     r8d, 1DEh; Size
0x1800133da  movdqu  xmmword ptr cs:pProperties.clsid.Data1, xmm0
0x1800133e2  call    memset_0
0x1800133e7  movups  xmm0, xmmword ptr cs:aCopyrightMicro; "Copyright Microsoft"
0x1800133ee  xor     edx, edx; Val
0x1800133f0  mov     r8d, 1D8h; Size
0x1800133f6  movups  xmm1, xmmword ptr cs:aCopyrightMicro+10h; "t Microsoft"
0x1800133fd  lea     rcx, pProperties.szCopyrightInfo+28h; void *
0x180013404  movups  xmmword ptr cs:pProperties.szCopyrightInfo, xmm0
0x18001340b  movsd   xmm0, qword ptr cs:aCopyrightMicro+20h; "oft"
0x180013413  movsd   qword ptr cs:pProperties.szCopyrightInfo+20h, xmm0
0x18001341b  movups  xmmword ptr cs:pProperties.szCopyrightInfo+10h, xmm1
0x180013422  call    memset_0
0x180013427  movups  xmm0, xmmword ptr cs:_GUID_fd7f2b29_24d0_4b5c_b177_592c39f9ca10.Data1
0x18001342e  mov     eax, 1
0x180013433  mov     cs:pProperties.u32MaxInstances, 0FFFFFFFFh
0x18001343d  mov     cs:pProperties.u32MajorVersion, eax
0x180013443  movdqu  xmmword ptr cs:pProperties.iidAPOInterfaceList.Data1, xmm0
0x18001344b  mov     cs:pProperties.u32MinorVersion, eax
0x180013451  mov     cs:pProperties.u32MinInputConnections, eax
0x180013457  mov     cs:pProperties.u32MaxInputConnections, eax
0x18001345d  mov     cs:pProperties.u32MinOutputConnections, eax
0x180013463  mov     cs:pProperties.u32MaxOutputConnections, eax
0x180013469  mov     cs:pProperties.u32NumAPOInterfaces, eax
0x18001346f  add     rsp, 28h
0x180013473  retn
```
