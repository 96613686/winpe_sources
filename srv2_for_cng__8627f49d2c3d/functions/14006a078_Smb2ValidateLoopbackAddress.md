# Smb2ValidateLoopbackAddress

- ea: `0x14006a078`
- end: `0x14006a1b0`
- name: `Smb2ValidateLoopbackAddress`
- size: `312`
- prototype: `__int64 __fastcall(PCtxtHandle phContext, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400921f0`

## callees

- `0x14002019c`
- `0x1400224b8`
- `0x140038490`
- `0x140038980`
- `0x14006a078`

## import_xrefs

- `srvnet!SrvNetIsConnectionLoopback` at `0x14006a140`
- `srvnet!SrvNetIsConnectionLoopback` at `0x14006a140`
- `ksecdd!MapSecurityError` at `0x14006a0d2`
- `ksecdd!MapSecurityError` at `0x14006a0d2`
- `ksecdd!QueryContextAttributesW` at `0x14006a0c4`
- `ksecdd!QueryContextAttributesW` at `0x14006a0c4`

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
0x14006a078  mov     [rsp+arg_10], rbx
0x14006a07d  push    rdi
0x14006a07e  sub     rsp, 0C0h
0x14006a085  mov     rax, cs:__security_cookie
0x14006a08c  xor     rax, rsp
0x14006a08f  mov     [rsp+0C8h+var_18], rax
0x14006a097  mov     rdi, rdx
0x14006a09a  mov     [rsp+0C8h+pBuffer], 0
0x14006a0a2  mov     rbx, rcx
0x14006a0a5  xor     edx, edx; Val
0x14006a0a7  lea     rcx, [rsp+0C8h+var_98]; void *
0x14006a0ac  mov     r8d, 80h; Size
0x14006a0b2  call    memset
0x14006a0b7  lea     r8, [rsp+0C8h+pBuffer]; pBuffer
0x14006a0bc  mov     edx, 25h ; '%'; ulAttribute
0x14006a0c1  mov     rcx, rbx; phContext
0x14006a0c4  call    cs:__imp_QueryContextAttributesW
0x14006a0cb  nop     dword ptr [rax+rax+00h]
0x14006a0d0  mov     ecx, eax; SecStatus
0x14006a0d2  call    cs:__imp_MapSecurityError
0x14006a0d9  nop     dword ptr [rax+rax+00h]
0x14006a0de  mov     ebx, eax
0x14006a0e0  cmp     eax, 0C00000BBh
0x14006a0e5  jnz     short loc_14006A0EE
0x14006a0e7  xor     ebx, ebx
0x14006a0e9  jmp     loc_14006A18C
0x14006a0ee  test    ebx, ebx
0x14006a0f0  jns     short loc_14006A132
0x14006a0f2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a0f9  lea     rax, WPP_GLOBAL_Control
0x14006a100  cmp     rcx, rax
0x14006a103  jz      loc_14006A18C
0x14006a109  test    dword ptr [rcx+2Ch], 20000h
0x14006a110  jz      short loc_14006A18C
0x14006a112  cmp     byte ptr [rcx+29h], 1
0x14006a116  jb      short loc_14006A18C
0x14006a118  mov     rcx, [rcx+18h]
0x14006a11c  lea     r8, WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids
0x14006a123  mov     edx, 26h ; '&'
0x14006a128  mov     r9d, ebx
0x14006a12b  call    WPP_SF_d
0x14006a130  jmp     short loc_14006A18C
0x14006a132  cmp     [rsp+0C8h+pBuffer], 0
0x14006a137  jz      short loc_14006A18C
0x14006a139  mov     rcx, [rdi+1E0h]
0x14006a140  call    cs:__imp_SrvNetIsConnectionLoopback
0x14006a147  nop     dword ptr [rax+rax+00h]
0x14006a14c  test    al, al
0x14006a14e  jnz     short loc_14006A18C
0x14006a150  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a157  lea     rax, WPP_GLOBAL_Control
0x14006a15e  cmp     rcx, rax
0x14006a161  jz      short loc_14006A187
0x14006a163  test    dword ptr [rcx+2Ch], 20000h
0x14006a16a  jz      short loc_14006A187
0x14006a16c  cmp     byte ptr [rcx+29h], 1
0x14006a170  jb      short loc_14006A187
0x14006a172  mov     rcx, [rcx+18h]
0x14006a176  lea     r8, WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids
0x14006a17d  mov     edx, 27h ; '''
0x14006a182  call    WPP_SF_
0x14006a187  mov     ebx, 0C0000022h
0x14006a18c  mov     eax, ebx
0x14006a18e  mov     rcx, [rsp+0C8h+var_18]
0x14006a196  xor     rcx, rsp; StackCookie
0x14006a199  call    __security_check_cookie
0x14006a19e  mov     rbx, [rsp+0C8h+arg_10]
0x14006a1a6  add     rsp, 0C0h
0x14006a1ad  pop     rdi
0x14006a1ae  retn
```
