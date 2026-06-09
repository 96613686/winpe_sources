# _dynamic_initializer_for__s_GFXAPOCAPXReg__

- ea: `0x180013480`
- end: `0x180013534`
- name: `_dynamic_initializer_for__s_GFXAPOCAPXReg__`
- size: `180`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180015ea8`

## string_xrefs

- `0x1800134a7`: `Copyright Microsoft`

## pseudocode

```c
__int64 dynamic_initializer_for__s_GFXAPOCAPXReg__()
{
  __int64 result; // rax

  clsid.clsid = CLSID_CWMAudioCAPXGFXAPO;
  memset_0(&clsid.szFriendlyName[22], 0, 0x1D4u);
  wcscpy(clsid.szCopyrightInfo, L"Copyright Microsoft");
  memset_0(&clsid.szCopyrightInfo[20], 0, 0x1D8u);
  result = 1;
  clsid.u32MaxInstances = -1;
  clsid.u32MajorVersion = 1;
  clsid.iidAPOInterfaceList[0] = GUID_fd7f2b29_24d0_4b5c_b177_592c39f9ca10;
  clsid.u32MinorVersion = 1;
  clsid.u32MinInputConnections = 1;
  clsid.u32MaxInputConnections = 1;
  clsid.u32MinOutputConnections = 1;
  clsid.u32MaxOutputConnections = 1;
  clsid.u32NumAPOInterfaces = 1;
  return result;
}

```

## disassembly

```asm
0x180013480  sub     rsp, 28h
0x180013484  movups  xmm0, xmmword ptr cs:CLSID_CWMAudioCAPXGFXAPO.Data1
0x18001348b  xor     edx, edx; Val
0x18001348d  lea     rcx, clsid.szFriendlyName+2Ch; void *
0x180013494  mov     r8d, 1D4h; Size
0x18001349a  movdqu  xmmword ptr cs:clsid.clsid.Data1, xmm0
0x1800134a2  call    memset_0
0x1800134a7  movups  xmm0, xmmword ptr cs:aCopyrightMicro; "Copyright Microsoft"
0x1800134ae  xor     edx, edx; Val
0x1800134b0  mov     r8d, 1D8h; Size
0x1800134b6  movups  xmm1, xmmword ptr cs:aCopyrightMicro+10h; "t Microsoft"
0x1800134bd  lea     rcx, clsid.szCopyrightInfo+28h; void *
0x1800134c4  movups  xmmword ptr cs:clsid.szCopyrightInfo, xmm0
0x1800134cb  movsd   xmm0, qword ptr cs:aCopyrightMicro+20h; "oft"
0x1800134d3  movsd   qword ptr cs:clsid.szCopyrightInfo+20h, xmm0
0x1800134db  movups  xmmword ptr cs:clsid.szCopyrightInfo+10h, xmm1
0x1800134e2  call    memset_0
0x1800134e7  movups  xmm0, xmmword ptr cs:_GUID_fd7f2b29_24d0_4b5c_b177_592c39f9ca10.Data1
0x1800134ee  mov     eax, 1
0x1800134f3  mov     cs:clsid.u32MaxInstances, 0FFFFFFFFh
0x1800134fd  mov     cs:clsid.u32MajorVersion, eax
0x180013503  movdqu  xmmword ptr cs:clsid.iidAPOInterfaceList.Data1, xmm0
0x18001350b  mov     cs:clsid.u32MinorVersion, eax
0x180013511  mov     cs:clsid.u32MinInputConnections, eax
0x180013517  mov     cs:clsid.u32MaxInputConnections, eax
0x18001351d  mov     cs:clsid.u32MinOutputConnections, eax
0x180013523  mov     cs:clsid.u32MaxOutputConnections, eax
0x180013529  mov     cs:clsid.u32NumAPOInterfaces, eax
0x18001352f  add     rsp, 28h
0x180013533  retn
```
