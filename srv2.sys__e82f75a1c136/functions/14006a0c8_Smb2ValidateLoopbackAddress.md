# Smb2ValidateLoopbackAddress

- ea: `0x14006a0c8`
- end: `0x14006a1bd`
- name: `Smb2ValidateLoopbackAddress`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400921f0`

## callees

- `0x14002019c`
- `0x1400224b8`
- `0x14006a0c8`

## import_xrefs

- `srvnet!SrvNetIsConnectionLoopback` at `0x14006a163`
- `srvnet!SrvNetIsConnectionLoopback` at `0x14006a163`
- `ksecdd!MapSecurityError` at `0x14006a0f5`
- `ksecdd!MapSecurityError` at `0x14006a0f5`
- `ksecdd!QueryContextAttributesW` at `0x14006a0e7`
- `ksecdd!QueryContextAttributesW` at `0x14006a0e7`

## pseudocode

```c
__int64 __fastcall Smb2ValidateLoopbackAddress(struct _SecHandle *a1, __int64 a2)
{
  SECURITY_STATUS v3; // eax
  NTSTATUS v4; // ebx
  int pBuffer; // [rsp+40h] [rbp+18h] BYREF

  pBuffer = 0;
  v3 = QueryContextAttributesW(a1, 0x25u, &pBuffer);
  v4 = MapSecurityError(v3);
  if ( v4 == -1073741637 )
  {
    return 0;
  }
  else if ( v4 >= 0 )
  {
    if ( pBuffer && !(unsigned __int8)SrvNetIsConnectionLoopback(*(_QWORD *)(a2 + 480)) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_e0e359be8cf43294cb4320ac1055cae3_Traceguids);
      }
      return (unsigned int)-1073741790;
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_e0e359be8cf43294cb4320ac1055cae3_Traceguids, (unsigned int)v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14006a0c8  mov     [rsp+arg_0], rbx
0x14006a0cd  push    rdi
0x14006a0ce  sub     rsp, 20h
0x14006a0d2  mov     rdi, rdx
0x14006a0d5  mov     [rsp+28h+pBuffer], 0
0x14006a0dd  mov     edx, 25h ; '%'; ulAttribute
0x14006a0e2  lea     r8, [rsp+28h+pBuffer]; pBuffer
0x14006a0e7  call    cs:__imp_QueryContextAttributesW
0x14006a0ee  nop     dword ptr [rax+rax+00h]
0x14006a0f3  mov     ecx, eax; SecStatus
0x14006a0f5  call    cs:__imp_MapSecurityError
0x14006a0fc  nop     dword ptr [rax+rax+00h]
0x14006a101  mov     ebx, eax
0x14006a103  cmp     eax, 0C00000BBh
0x14006a108  jnz     short loc_14006A111
0x14006a10a  xor     ebx, ebx
0x14006a10c  jmp     loc_14006A1AF
0x14006a111  test    ebx, ebx
0x14006a113  jns     short loc_14006A155
0x14006a115  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a11c  lea     rax, WPP_GLOBAL_Control
0x14006a123  cmp     rcx, rax
0x14006a126  jz      loc_14006A1AF
0x14006a12c  test    dword ptr [rcx+2Ch], 20000h
0x14006a133  jz      short loc_14006A1AF
0x14006a135  cmp     byte ptr [rcx+29h], 1
0x14006a139  jb      short loc_14006A1AF
0x14006a13b  mov     rcx, [rcx+18h]
0x14006a13f  lea     r8, WPP_e0e359be8cf43294cb4320ac1055cae3_Traceguids
0x14006a146  mov     edx, 26h ; '&'
0x14006a14b  mov     r9d, ebx
0x14006a14e  call    WPP_SF_d
0x14006a153  jmp     short loc_14006A1AF
0x14006a155  cmp     [rsp+28h+pBuffer], 0
0x14006a15a  jz      short loc_14006A1AF
0x14006a15c  mov     rcx, [rdi+1E0h]
0x14006a163  call    cs:__imp_SrvNetIsConnectionLoopback
0x14006a16a  nop     dword ptr [rax+rax+00h]
0x14006a16f  test    al, al
0x14006a171  jnz     short loc_14006A1AF
0x14006a173  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a17a  lea     rax, WPP_GLOBAL_Control
0x14006a181  cmp     rcx, rax
0x14006a184  jz      short loc_14006A1AA
0x14006a186  test    dword ptr [rcx+2Ch], 20000h
0x14006a18d  jz      short loc_14006A1AA
0x14006a18f  cmp     byte ptr [rcx+29h], 1
0x14006a193  jb      short loc_14006A1AA
0x14006a195  mov     rcx, [rcx+18h]
0x14006a199  lea     r8, WPP_e0e359be8cf43294cb4320ac1055cae3_Traceguids
0x14006a1a0  mov     edx, 27h ; '''
0x14006a1a5  call    WPP_SF_
0x14006a1aa  mov     ebx, 0C0000022h
0x14006a1af  mov     eax, ebx
0x14006a1b1  mov     rbx, [rsp+28h+arg_0]
0x14006a1b6  add     rsp, 20h
0x14006a1ba  pop     rdi
0x14006a1bb  retn
```
