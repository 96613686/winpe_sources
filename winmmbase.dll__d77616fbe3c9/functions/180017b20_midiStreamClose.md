# midiStreamClose

- ea: `0x180017b20`
- end: `0x180017cba`
- name: `midiStreamClose`
- size: `410`
- prototype: `MMRESULT __stdcall(HMIDISTRM hms)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180007560`
- `0x180007d70`
- `0x18000c570`
- `0x18000e0d0`
- `0x180011dac`
- `0x1800174ec`
- `0x180017b20`
- `0x180017cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017bc4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017bc4`

## pseudocode

```c
MMRESULT __stdcall midiStreamClose(HMIDISTRM hms)
{
  PVOID *v3; // rcx
  unsigned int v4; // esi
  HMIDISTRM i; // rdi
  unsigned int v6; // eax
  struct _MMDRV *v7; // rcx

  if ( !(unsigned int)ValidateHandle(hms, 9) )
    return 5;
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_df1b99d7603f3114e281f38f1879dcaa_Traceguids, hms);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  v4 = 0;
  for ( i = hms + 8; v4 < *((_DWORD *)hms + 7); i += 20 )
  {
    if ( ((_BYTE)i[8] & 6) == 6 )
    {
      v6 = midiStreamMessage(i, 4, 0);
      if ( v6 || ((_BYTE)i[8] & 1) != 0 )
      {
        v3 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_17;
        }
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_df1b99d7603f3114e281f38f1879dcaa_Traceguids, v6);
      }
      else
      {
        DeleteCriticalSection((LPCRITICAL_SECTION)i + 1);
        v7 = *(struct _MMDRV **)i;
        *((_DWORD *)i + 8) &= ~8u;
        mregDecUsagePtr(v7);
      }
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_17:
    ++v4;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_DWORD *)v3 + 7) & 0x400000) != 0 && *((_BYTE *)v3 + 25) )
    WPP_SF_q(v3[2], 25, &WPP_df1b99d7603f3114e281f38f1879dcaa_Traceguids, hms);
  DriverCallback(*((_QWORD *)hms + 1), *((unsigned __int16 *)hms + 1), (HDRVR)hms, 0x3C8u, *((_QWORD *)hms + 2), 0, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_df1b99d7603f3114e281f38f1879dcaa_Traceguids, hms);
  }
  FreeHandle((__int64)hms);
  return 0;
}

```

## disassembly

```asm
0x180017b20  push    rbx
0x180017b22  push    rsi
0x180017b23  push    rdi
0x180017b24  push    r12
0x180017b26  push    r15
0x180017b28  sub     rsp, 40h
0x180017b2c  mov     edx, 9
0x180017b31  mov     rbx, rcx
0x180017b34  call    ValidateHandle
0x180017b39  test    eax, eax
0x180017b3b  jnz     short loc_180017B47
0x180017b3d  mov     eax, 5
0x180017b42  jmp     loc_180017CAE
0x180017b47  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b4e  lea     r12, WPP_GLOBAL_Control
0x180017b55  mov     r15d, 400000h
0x180017b5b  cmp     rcx, r12
0x180017b5e  jz      short loc_180017B8B
0x180017b60  test    [rcx+1Ch], r15d
0x180017b64  jz      short loc_180017B8B
0x180017b66  cmp     byte ptr [rcx+19h], 1
0x180017b6a  jb      short loc_180017B8B
0x180017b6c  mov     rcx, [rcx+10h]
0x180017b70  lea     r8, WPP_df1b99d7603f3114e281f38f1879dcaa_Traceguids
0x180017b77  mov     edx, 17h
0x180017b7c  mov     r9, rbx
0x180017b7f  call    WPP_SF_q
0x180017b84  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b8b  xor     esi, esi
0x180017b8d  lea     rdi, [rbx+20h]
0x180017b91  cmp     [rbx+1Ch], esi
0x180017b94  jbe     loc_180017C1A
0x180017b9a  mov     eax, [rdi+20h]
0x180017b9d  and     eax, 6
0x180017ba0  cmp     al, 6
0x180017ba2  jnz     short loc_180017C0F
0x180017ba4  xor     r9d, r9d
0x180017ba7  xor     r8d, r8d
0x180017baa  mov     rcx, rdi
0x180017bad  lea     edx, [r9+4]
0x180017bb1  call    midiStreamMessage
0x180017bb6  test    eax, eax
0x180017bb8  jnz     short loc_180017BD8
0x180017bba  test    byte ptr [rdi+20h], 1
0x180017bbe  jnz     short loc_180017BD8
0x180017bc0  lea     rcx, [rdi+28h]; lpCriticalSection
0x180017bc4  call    cs:__imp_DeleteCriticalSection
0x180017bca  mov     rcx, [rdi]; struct _MMDRV *
0x180017bcd  and     dword ptr [rdi+20h], 0FFFFFFF7h
0x180017bd1  call    mregDecUsagePtr
0x180017bd6  jmp     short loc_180017C08
0x180017bd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180017bdf  cmp     rcx, r12
0x180017be2  jz      short loc_180017C0F
0x180017be4  test    [rcx+1Ch], r15d
0x180017be8  jz      short loc_180017C0F
0x180017bea  cmp     byte ptr [rcx+19h], 1
0x180017bee  jb      short loc_180017C0F
0x180017bf0  mov     rcx, [rcx+10h]
0x180017bf4  lea     r8, WPP_df1b99d7603f3114e281f38f1879dcaa_Traceguids
0x180017bfb  mov     edx, 18h
0x180017c00  mov     r9d, eax
0x180017c03  call    WPP_SF_D
0x180017c08  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c0f  inc     esi
0x180017c11  add     rdi, 50h ; 'P'
0x180017c15  cmp     esi, [rbx+1Ch]
0x180017c18  jb      short loc_180017B9A
0x180017c1a  cmp     rcx, r12
0x180017c1d  jz      short loc_180017C43
0x180017c1f  test    [rcx+1Ch], r15d
0x180017c23  jz      short loc_180017C43
0x180017c25  cmp     byte ptr [rcx+19h], 1
0x180017c29  jb      short loc_180017C43
0x180017c2b  mov     rcx, [rcx+10h]
0x180017c2f  lea     r8, WPP_df1b99d7603f3114e281f38f1879dcaa_Traceguids
0x180017c36  mov     edx, 19h
0x180017c3b  mov     r9, rbx
0x180017c3e  call    WPP_SF_q
0x180017c43  mov     rax, [rbx+10h]
0x180017c47  mov     r9d, 3C8h; dwMsg
0x180017c4d  movzx   edx, word ptr [rbx+2]; dwFlags
0x180017c51  mov     r8, rbx; hDevice
0x180017c54  mov     rcx, [rbx+8]; dwCallback
0x180017c58  mov     [rsp+68h+dwParam2], 0; dwParam2
0x180017c61  mov     [rsp+68h+dwParam1], 0; dwParam1
0x180017c6a  mov     [rsp+68h+dwUser], rax; dwUser
0x180017c6f  call    DriverCallback
0x180017c74  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c7b  cmp     rcx, r12
0x180017c7e  jz      short loc_180017CA4
0x180017c80  test    [rcx+1Ch], r15d
0x180017c84  jz      short loc_180017CA4
0x180017c86  cmp     byte ptr [rcx+19h], 1
0x180017c8a  jb      short loc_180017CA4
0x180017c8c  mov     rcx, [rcx+10h]
0x180017c90  lea     r8, WPP_df1b99d7603f3114e281f38f1879dcaa_Traceguids
0x180017c97  mov     edx, 1Ah
0x180017c9c  mov     r9, rbx
0x180017c9f  call    WPP_SF_q
0x180017ca4  mov     rcx, rbx
0x180017ca7  call    FreeHandle
0x180017cac  xor     eax, eax
0x180017cae  add     rsp, 40h
0x180017cb2  pop     r15
0x180017cb4  pop     r12
0x180017cb6  pop     rdi
0x180017cb7  pop     rsi
0x180017cb8  pop     rbx
0x180017cb9  retn
```
