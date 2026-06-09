# MSMSecDeinitialize

- ea: `0x180052b00`
- end: `0x180052c26`
- name: `MSMSecDeinitialize`
- size: `294`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000892c`
- `0x180008998`
- `0x180050648`
- `0x180052b00`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180052bdf`
- `MobileNetworking!ReleaseWriteLock` at `0x180052bdf`
- `MobileNetworking!AcquireWriteLock` at `0x180052b56`
- `MobileNetworking!AcquireWriteLock` at `0x180052b56`

## pseudocode

```c
__int64 MSMSecDeinitialize()
{
  int v0; // edx
  const char *v1; // rcx
  unsigned int v2; // ebx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 14, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
  AcquireWriteLock(&g_MSMSecState, qword_1800AEF28, "MSMSecDeinitialize", 65);
  v1 = (const char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 15, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
    v1 = (const char *)WPP_GLOBAL_Control;
  }
  v2 = 0;
  if ( g_MSMSecState )
  {
    DecrementMSMSecRefCountEx(v1, v0);
  }
  else
  {
    v2 = 21;
    if ( v1 != (const char *)&WPP_GLOBAL_Control && (v1[68] & 1) != 0 )
      WPP_SF_(*((_QWORD *)v1 + 7), 16, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
  }
  ReleaseWriteLock(&g_MSMSecState, qword_1800AEF28, "MSMSecDeinitialize", 78);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x180052b00  mov     [rsp+arg_0], rbx
0x180052b05  push    rsi
0x180052b06  sub     rsp, 20h
0x180052b0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180052b11  lea     rsi, WPP_GLOBAL_Control
0x180052b18  cmp     rcx, rsi
0x180052b1b  jz      short loc_180052B3B
0x180052b1d  test    dword ptr [rcx+44h], 100h
0x180052b24  jz      short loc_180052B3B
0x180052b26  mov     rcx, [rcx+38h]
0x180052b2a  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180052b31  mov     edx, 0Eh
0x180052b36  call    WPP_SF_
0x180052b3b  mov     r9d, 41h ; 'A'
0x180052b41  lea     r8, aMsmsecdeinitia_3; "MSMSecDeinitialize"
0x180052b48  lea     rdx, qword_1800AEF28
0x180052b4f  lea     rcx, ?g_MSMSecState@@3UMSMSEC_GLOBAL_STATE@@A; MSMSEC_GLOBAL_STATE g_MSMSecState
0x180052b56  call    cs:__imp_AcquireWriteLock
0x180052b5d  nop     dword ptr [rax+rax+00h]
0x180052b62  mov     rcx, cs:WPP_GLOBAL_Control
0x180052b69  cmp     rcx, rsi
0x180052b6c  jz      short loc_180052B90
0x180052b6e  test    byte ptr [rcx+44h], 20h
0x180052b72  jz      short loc_180052B90
0x180052b74  mov     rcx, [rcx+38h]
0x180052b78  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180052b7f  mov     edx, 0Fh
0x180052b84  call    WPP_SF_
0x180052b89  mov     rcx, cs:WPP_GLOBAL_Control; char *
0x180052b90  xor     ebx, ebx
0x180052b92  cmp     cs:?g_MSMSecState@@3UMSMSEC_GLOBAL_STATE@@A, ebx; MSMSEC_GLOBAL_STATE g_MSMSecState
0x180052b98  jnz     short loc_180052BBF
0x180052b9a  mov     ebx, 15h
0x180052b9f  cmp     rcx, rsi
0x180052ba2  jz      short loc_180052BC4
0x180052ba4  test    byte ptr [rcx+44h], 1
0x180052ba8  jz      short loc_180052BC4
0x180052baa  mov     rcx, [rcx+38h]
0x180052bae  lea     edx, [rbx-5]
0x180052bb1  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180052bb8  call    WPP_SF_
0x180052bbd  jmp     short loc_180052BC4
0x180052bbf  call    ?DecrementMSMSecRefCountEx@@YAXPEBDH@Z; DecrementMSMSecRefCountEx(char const *,int)
0x180052bc4  mov     r9d, 4Eh ; 'N'
0x180052bca  lea     r8, aMsmsecdeinitia_3; "MSMSecDeinitialize"
0x180052bd1  lea     rdx, qword_1800AEF28
0x180052bd8  lea     rcx, ?g_MSMSecState@@3UMSMSEC_GLOBAL_STATE@@A; MSMSEC_GLOBAL_STATE g_MSMSecState
0x180052bdf  call    cs:__imp_ReleaseWriteLock
0x180052be6  nop     dword ptr [rax+rax+00h]
0x180052beb  mov     rcx, cs:WPP_GLOBAL_Control
0x180052bf2  cmp     rcx, rsi
0x180052bf5  jz      short loc_180052C18
0x180052bf7  test    dword ptr [rcx+44h], 100h
0x180052bfe  jz      short loc_180052C18
0x180052c00  mov     rcx, [rcx+38h]
0x180052c04  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180052c0b  mov     edx, 11h
0x180052c10  mov     r9d, ebx
0x180052c13  call    WPP_SF_d
0x180052c18  mov     eax, ebx
0x180052c1a  mov     rbx, [rsp+28h+arg_0]
0x180052c1f  add     rsp, 20h
0x180052c23  pop     rsi
0x180052c24  retn
```
