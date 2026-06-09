# Smb2ValidateLoopbackAddress

- ea: `0x14006a0c8`
- end: `0x14006a200`
- name: `Smb2ValidateLoopbackAddress`
- size: `312`
- prototype: `__int64 __fastcall(PCtxtHandle phContext)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140092240`

## callees

- `0x14002019c`
- `0x1400224b8`
- `0x140038490`
- `0x140038980`
- `0x14006a0c8`

## import_xrefs

- `srvnet!SrvNetIsConnectionLoopback` at `0x14006a190`
- `srvnet!SrvNetIsConnectionLoopback` at `0x14006a190`
- `ksecdd!MapSecurityError` at `0x14006a122`
- `ksecdd!MapSecurityError` at `0x14006a122`
- `ksecdd!QueryContextAttributesW` at `0x14006a114`
- `ksecdd!QueryContextAttributesW` at `0x14006a114`

## pseudocode

```c
__int64 __fastcall Smb2ValidateLoopbackAddress(PCtxtHandle phContext, __int64 a2)
{
  SECURITY_STATUS ContextAttributesW; // eax
  NTSTATUS v5; // ebx
  _DWORD pBuffer[36]; // [rsp+20h] [rbp-A8h] BYREF

  pBuffer[0] = 0;
  memset(&pBuffer[4], 0, 0x80u);
  ContextAttributesW = QueryContextAttributesW(phContext, 0x25u, pBuffer);
  v5 = MapSecurityError(ContextAttributesW);
  if ( v5 == -1073741637 )
  {
    return 0;
  }
  else if ( v5 >= 0 )
  {
    if ( pBuffer[0] && !(unsigned __int8)SrvNetIsConnectionLoopback(*(_QWORD *)(a2 + 480)) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids);
      }
      return (unsigned int)-1073741790;
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids, (unsigned int)v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14006a0c8  mov     [rsp+arg_10], rbx
0x14006a0cd  push    rdi
0x14006a0ce  sub     rsp, 0C0h
0x14006a0d5  mov     rax, cs:__security_cookie
0x14006a0dc  xor     rax, rsp
0x14006a0df  mov     [rsp+0C8h+var_18], rax
0x14006a0e7  mov     rdi, rdx
0x14006a0ea  mov     [rsp+0C8h+pBuffer], 0
0x14006a0f2  mov     rbx, rcx
0x14006a0f5  xor     edx, edx; Val
0x14006a0f7  lea     rcx, [rsp+0C8h+var_98]; void *
0x14006a0fc  mov     r8d, 80h; Size
0x14006a102  call    memset
0x14006a107  lea     r8, [rsp+0C8h+pBuffer]; pBuffer
0x14006a10c  mov     edx, 25h ; '%'; ulAttribute
0x14006a111  mov     rcx, rbx; phContext
0x14006a114  call    cs:__imp_QueryContextAttributesW
0x14006a11b  nop     dword ptr [rax+rax+00h]
0x14006a120  mov     ecx, eax; SecStatus
0x14006a122  call    cs:__imp_MapSecurityError
0x14006a129  nop     dword ptr [rax+rax+00h]
0x14006a12e  mov     ebx, eax
0x14006a130  cmp     eax, 0C00000BBh
0x14006a135  jnz     short loc_14006A13E
0x14006a137  xor     ebx, ebx
0x14006a139  jmp     loc_14006A1DC
0x14006a13e  test    ebx, ebx
0x14006a140  jns     short loc_14006A182
0x14006a142  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a149  lea     rax, WPP_GLOBAL_Control
0x14006a150  cmp     rcx, rax
0x14006a153  jz      loc_14006A1DC
0x14006a159  test    dword ptr [rcx+2Ch], 20000h
0x14006a160  jz      short loc_14006A1DC
0x14006a162  cmp     byte ptr [rcx+29h], 1
0x14006a166  jb      short loc_14006A1DC
0x14006a168  mov     rcx, [rcx+18h]
0x14006a16c  lea     r8, WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids
0x14006a173  mov     edx, 26h ; '&'
0x14006a178  mov     r9d, ebx
0x14006a17b  call    WPP_SF_d
0x14006a180  jmp     short loc_14006A1DC
0x14006a182  cmp     [rsp+0C8h+pBuffer], 0
0x14006a187  jz      short loc_14006A1DC
0x14006a189  mov     rcx, [rdi+1E0h]
0x14006a190  call    cs:__imp_SrvNetIsConnectionLoopback
0x14006a197  nop     dword ptr [rax+rax+00h]
0x14006a19c  test    al, al
0x14006a19e  jnz     short loc_14006A1DC
0x14006a1a0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a1a7  lea     rax, WPP_GLOBAL_Control
0x14006a1ae  cmp     rcx, rax
0x14006a1b1  jz      short loc_14006A1D7
0x14006a1b3  test    dword ptr [rcx+2Ch], 20000h
0x14006a1ba  jz      short loc_14006A1D7
0x14006a1bc  cmp     byte ptr [rcx+29h], 1
0x14006a1c0  jb      short loc_14006A1D7
0x14006a1c2  mov     rcx, [rcx+18h]
0x14006a1c6  lea     r8, WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids
0x14006a1cd  mov     edx, 27h ; '''
0x14006a1d2  call    WPP_SF_
0x14006a1d7  mov     ebx, 0C0000022h
0x14006a1dc  mov     eax, ebx
0x14006a1de  mov     rcx, [rsp+0C8h+var_18]
0x14006a1e6  xor     rcx, rsp; StackCookie
0x14006a1e9  call    __security_check_cookie
0x14006a1ee  mov     rbx, [rsp+0C8h+arg_10]
0x14006a1f6  add     rsp, 0C0h
0x14006a1fd  pop     rdi
0x14006a1fe  retn
```
