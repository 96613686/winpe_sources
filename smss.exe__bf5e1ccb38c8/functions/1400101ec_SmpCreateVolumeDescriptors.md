# SmpCreateVolumeDescriptors

- ea: `0x1400101ec`
- end: `0x14001033b`
- name: `SmpCreateVolumeDescriptors`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14000fcf8`

## callees

- `0x14000d4c0`
- `0x14000e5a8`
- `0x14000fed0`
- `0x1400101ec`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x140010241`
- `ntdll!NtQueryInformationProcess` at `0x140010241`
- `ntdll!RtlInitUnicodeStringEx` at `0x140010287`
- `ntdll!RtlInitUnicodeStringEx` at `0x1400102a7`
- `ntdll!RtlInitUnicodeStringEx` at `0x140010287`
- `ntdll!RtlInitUnicodeStringEx` at `0x1400102a7`

## string_xrefs

- `0x140010250`: `SmpCreateVolumeDescriptors`

## pseudocode

```c
__int64 SmpCreateVolumeDescriptors()
{
  NTSTATUS InformationProcess; // eax
  unsigned int v1; // ebx
  unsigned __int16 i; // bx
  int v4; // eax
  struct _UNICODE_STRING v5; // [rsp+30h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-9h] BYREF
  _OWORD ProcessInformation[2]; // [rsp+50h] [rbp+7h] BYREF
  __int64 v8; // [rsp+70h] [rbp+27h]
  wchar_t pszDest[8]; // [rsp+78h] [rbp+2Fh] BYREF
  wchar_t SourceString[8]; // [rsp+88h] [rbp+3Fh] BYREF

  v8 = 0;
  DestinationString = 0;
  v5 = 0;
  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  InformationProcess = NtQueryInformationProcess(
                         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                         ProcessDeviceMap,
                         ProcessInformation,
                         0x24u,
                         0);
  v1 = InformationProcess;
  if ( InformationProcess >= 0 )
  {
    RtlStringCbCopyW(pszDest, 0x10u, L"\\??\\A:\\");
    RtlInitUnicodeStringEx(&DestinationString, pszDest);
    RtlStringCbCopyW(SourceString, 0x10u, L"\\??\\A:");
    RtlInitUnicodeStringEx(&v5, SourceString);
    for ( i = 67; i <= 0x5Au; ++i )
    {
      v4 = ProcessInformation[0];
      if ( _bittest(&v4, (unsigned __int8)(i - 65)) && (SmpPagefileOnOsVolume != 1 || i == SmpOsVolumeLetter) )
      {
        DestinationString.Buffer[4] = i;
        v5.Buffer[4] = i;
        SmpCreateVolumeDescriptor(i, &DestinationString, &v5);
      }
    }
    return SmpVolumeDescriptorList == (_QWORD)&SmpVolumeDescriptorList ? 0xC00000E9 : 0;
  }
  else
  {
    SmpLogFailure("SmpCreateVolumeDescriptors", 1579, (unsigned int)InformationProcess);
    return v1;
  }
}

```

## disassembly

```asm
0x1400101ec  mov     [rsp-8+arg_0], rbx
0x1400101f1  mov     [rsp-8+arg_8], rdi
0x1400101f6  push    rbp
0x1400101f7  lea     rbp, [rsp-57h]
0x1400101fc  sub     rsp, 0A0h
0x140010203  mov     rax, cs:__security_cookie
0x14001020a  xor     rax, rsp
0x14001020d  mov     [rbp+57h+var_8], rax
0x140010211  xor     eax, eax
0x140010213  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x140010217  xorps   xmm0, xmm0
0x14001021a  mov     [rbp+57h+var_30], rax
0x14001021e  xorps   xmm1, xmm1
0x140010221  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x140010226  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14001022a  lea     r9d, [rax+24h]; ProcessInformationLength
0x14001022e  lea     edx, [rax+17h]; ProcessInformationClass
0x140010231  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140010235  movups  xmmword ptr [rbp+57h+var_70.Length], xmm1
0x140010239  movups  [rbp+57h+ProcessInformation], xmm0
0x14001023d  movups  [rbp+57h+var_40], xmm0
0x140010241  call    cs:__imp_NtQueryInformationProcess
0x140010247  mov     ebx, eax
0x140010249  test    eax, eax
0x14001024b  jns     short loc_140010268
0x14001024d  mov     r8d, eax
0x140010250  lea     rcx, aSmpcreatevolum_0; "SmpCreateVolumeDescriptors"
0x140010257  mov     edx, 62Bh
0x14001025c  call    SmpLogFailure
0x140010261  mov     eax, ebx
0x140010263  jmp     loc_14001031A
0x140010268  mov     ebx, 10h
0x14001026d  lea     r8, aA; "\\??\\A:\\"
0x140010274  mov     edx, ebx; cbDest
0x140010276  lea     rcx, [rbp+57h+pszDest]; pszDest
0x14001027a  call    RtlStringCbCopyW
0x14001027f  lea     rdx, [rbp+57h+pszDest]; SourceString
0x140010283  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140010287  call    cs:__imp_RtlInitUnicodeStringEx
0x14001028d  lea     r8, aA_0; "\\??\\A:"
0x140010294  mov     edx, ebx; cbDest
0x140010296  lea     rcx, [rbp+57h+SourceString]; pszDest
0x14001029a  call    RtlStringCbCopyW
0x14001029f  lea     rdx, [rbp+57h+SourceString]; SourceString
0x1400102a3  lea     rcx, [rbp+57h+var_70]; DestinationString
0x1400102a7  call    cs:__imp_RtlInitUnicodeStringEx
0x1400102ad  mov     ebx, 43h ; 'C'
0x1400102b2  lea     edi, [rbx-42h]
0x1400102b5  movzx   eax, bx
0x1400102b8  sub     eax, 41h ; 'A'
0x1400102bb  movzx   ecx, al
0x1400102be  mov     eax, dword ptr [rbp+57h+ProcessInformation]
0x1400102c1  bt      eax, ecx
0x1400102c4  jnb     short loc_1400102F7
0x1400102c6  cmp     cs:SmpPagefileOnOsVolume, edi
0x1400102cc  jnz     short loc_1400102D7
0x1400102ce  cmp     bx, cs:SmpOsVolumeLetter
0x1400102d5  jnz     short loc_1400102F7
0x1400102d7  mov     rax, [rbp+57h+DestinationString.Buffer]
0x1400102db  lea     r8, [rbp+57h+var_70]
0x1400102df  lea     rdx, [rbp+57h+DestinationString]
0x1400102e3  movzx   ecx, bx
0x1400102e6  mov     [rax+8], bx
0x1400102ea  mov     rax, [rbp+57h+var_70.Buffer]
0x1400102ee  mov     [rax+8], bx
0x1400102f2  call    SmpCreateVolumeDescriptor
0x1400102f7  add     bx, di
0x1400102fa  cmp     bx, 5Ah ; 'Z'
0x1400102fe  jbe     short loc_1400102B5
0x140010300  lea     rax, SmpVolumeDescriptorList
0x140010307  cmp     cs:SmpVolumeDescriptorList, rax
0x14001030e  setz    al
0x140010311  neg     al
0x140010313  sbb     eax, eax
0x140010315  and     eax, 0C00000E9h
0x14001031a  mov     rcx, [rbp+57h+var_8]
0x14001031e  xor     rcx, rsp; StackCookie
0x140010321  call    __security_check_cookie
0x140010326  lea     r11, [rsp+0A0h+var_s0]
0x14001032e  mov     rbx, [r11+10h]
0x140010332  mov     rdi, [r11+18h]
0x140010336  mov     rsp, r11
0x140010339  pop     rbp
0x14001033a  retn
```
