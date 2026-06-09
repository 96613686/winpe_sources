# Smb2UpdateSessionWithClaims

- ea: `0x140069d2c`
- end: `0x14006a072`
- name: `Smb2UpdateSessionWithClaims`
- size: `838`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400921f0`

## callees

- `0x14002019c`
- `0x1400224b8`
- `0x1400315dc`
- `0x140031d6c`
- `0x140068510`
- `0x140069d2c`
- `0x140077600`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140069e32`
- `ntoskrnl!RtlInitUnicodeString` at `0x140069e32`
- `ntoskrnl!NtClose` at `0x14006a044`
- `ntoskrnl!NtClose` at `0x14006a044`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140069f69`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140069f69`
- `ntoskrnl!NtSetInformationThread` at `0x140069f35`
- `ntoskrnl!NtSetInformationThread` at `0x140069f35`
- `srvnet!SrvLibS4U2SelfAuth` at `0x140069f0a`
- `srvnet!SrvLibS4U2SelfAuth` at `0x140069f0a`
- `ksecdd!FreeContextBuffer` at `0x14006a02f`
- `ksecdd!FreeContextBuffer` at `0x14006a02f`
- `ksecdd!MapSecurityError` at `0x140069dc5`
- `ksecdd!MapSecurityError` at `0x140069dc5`
- `ksecdd!QueryContextAttributesW` at `0x140069db7`
- `ksecdd!QueryContextAttributesW` at `0x140069db7`

## pseudocode

```c
__int64 __fastcall Smb2UpdateSessionWithClaims(__int64 a1, int a2)
{
  __int64 v2; // r15
  int v3; // r13d
  __int64 v4; // rdi
  NTSTATUS AuthenticationIdToken; // ebx
  SECURITY_STATUS v6; // eax
  USHORT Length; // dx
  unsigned __int16 v8; // cx
  int v9; // eax
  NTSTATUS v10; // eax
  void *v11; // rcx
  __int64 v13; // [rsp+40h] [rbp-30h] BYREF
  PWSTR v14; // [rsp+48h] [rbp-28h]
  __int64 v15; // [rsp+50h] [rbp-20h] BYREF
  PWSTR Buffer; // [rsp+58h] [rbp-18h]
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-10h] BYREF
  WCHAR *pBuffer; // [rsp+B0h] [rbp+40h] BYREF
  HANDLE ThreadInformation; // [rsp+B8h] [rbp+48h] BYREF

  v2 = *(_QWORD *)(a1 + 560);
  pBuffer = 0;
  DestinationString = 0;
  v13 = 0;
  v3 = a1;
  v14 = 0;
  v15 = 0;
  Buffer = 0;
  v4 = *(_QWORD *)(v2 + 48);
  ThreadInformation = 0;
  if ( !v4 || !*(_QWORD *)(v4 + 32) && !*(_QWORD *)(v4 + 40) || *(_BYTE *)(v4 + 24) )
    return 3221225480LL;
  if ( Smb2S4U2SelfContext )
  {
    v6 = QueryContextAttributesW((PCtxtHandle)(v4 + 32), 1u, &pBuffer);
    AuthenticationIdToken = MapSecurityError(v6);
    if ( AuthenticationIdToken >= 0 )
    {
      if ( pBuffer && *pBuffer )
      {
        RtlInitUnicodeString(&DestinationString, pBuffer);
        Length = DestinationString.Length;
        v8 = 0;
        Buffer = DestinationString.Buffer;
        if ( DestinationString.Length >> 1 )
        {
          do
          {
            if ( DestinationString.Buffer[v8] == 92 )
              break;
            ++v8;
          }
          while ( v8 < (unsigned __int16)(DestinationString.Length >> 1) );
        }
        if ( DestinationString.Buffer[v8] == 92 )
        {
          LOWORD(v15) = 2 * v8;
          WORD1(v15) = 2 * v8;
          Length = DestinationString.Length - 2 * v8 - 2;
          v14 = &DestinationString.Buffer[v8 + 1];
        }
        else
        {
          LODWORD(v15) = 0;
          v14 = DestinationString.Buffer;
        }
        LOWORD(v13) = Length;
        WORD1(v13) = Length;
      }
      else
      {
        LOWORD(v13) = 0;
        LOWORD(v15) = 0;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_ZZ(
          WPP_GLOBAL_Control->AttachedDevice,
          52,
          (unsigned int)WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids,
          (unsigned int)&v15,
          (__int64)&v13);
      }
      v9 = SrvLibS4U2SelfAuth(Smb2S4U2SelfContext, &v13, &v15, &ThreadInformation);
      AuthenticationIdToken = v9;
      if ( v9 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u)
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            54,
            WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids,
            (unsigned int)v9);
        }
      }
      else
      {
        v10 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
        AuthenticationIdToken = v10;
        if ( v10 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u)
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              53,
              WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids,
              (unsigned int)v10);
          }
        }
        else
        {
          Smb2SecurityContextCaptureThreadToken(v4);
          if ( *(_BYTE *)(v4 + 24) )
          {
            v11 = *(void **)(v4 + 48);
            if ( v11 )
              AuthenticationIdToken = SeQueryAuthenticationIdToken(v11, (PLUID)(*(_QWORD *)(v2 + 32) + 160LL));
          }
          Smb2Revert();
        }
        if ( AuthenticationIdToken >= 0 )
          goto LABEL_44;
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u)
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids);
    }
  }
  else
  {
    AuthenticationIdToken = -1073741275;
  }
  if ( (byte_14004C339 & 0x40) != 0 )
    McTemplateK0hzr0hzr2q_EtwWriteTransfer(
      (unsigned __int16)v15 >> 1,
      a2,
      v3 + 584,
      (unsigned __int16)v13 >> 1,
      (__int64)v14,
      (unsigned __int16)v15 >> 1,
      (__int64)Buffer,
      AuthenticationIdToken);
LABEL_44:
  if ( pBuffer )
    FreeContextBuffer(pBuffer);
  if ( ThreadInformation )
    NtClose(ThreadInformation);
  return (unsigned int)AuthenticationIdToken;
}

```

## disassembly

```asm
0x140069d2c  mov     [rsp-38h+arg_10], rbx
0x140069d31  push    rbp
0x140069d32  push    rsi
0x140069d33  push    rdi
0x140069d34  push    r12
0x140069d36  push    r13
0x140069d38  push    r14
0x140069d3a  push    r15
0x140069d3c  mov     rbp, rsp
0x140069d3f  sub     rsp, 70h
0x140069d43  mov     r15, [rcx+230h]
0x140069d4a  xor     r12d, r12d
0x140069d4d  xorps   xmm0, xmm0
0x140069d50  mov     [rbp+pBuffer], r12
0x140069d54  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140069d58  mov     [rbp+var_30], r12
0x140069d5c  mov     r13, rcx
0x140069d5f  mov     [rbp+var_28], r12
0x140069d63  mov     [rbp+var_20], r12
0x140069d67  mov     [rbp+var_18], r12
0x140069d6b  mov     rdi, [r15+30h]
0x140069d6f  mov     [rbp+ThreadInformation], r12
0x140069d73  test    rdi, rdi
0x140069d76  jz      loc_14006A054
0x140069d7c  lea     rcx, [rdi+20h]; phContext
0x140069d80  cmp     [rcx], r12
0x140069d83  jnz     short loc_140069D8F
0x140069d85  cmp     [rdi+28h], r12
0x140069d89  jz      loc_14006A054
0x140069d8f  cmp     [rdi+18h], r12b
0x140069d93  jnz     loc_14006A054
0x140069d99  cmp     cs:Smb2S4U2SelfContext, r12
0x140069da0  jnz     short loc_140069DAC
0x140069da2  mov     ebx, 0C0000225h
0x140069da7  jmp     loc_140069FE6
0x140069dac  mov     esi, 1
0x140069db1  lea     r8, [rbp+pBuffer]; pBuffer
0x140069db5  mov     edx, esi; ulAttribute
0x140069db7  call    cs:__imp_QueryContextAttributesW
0x140069dbe  nop     dword ptr [rax+rax+00h]
0x140069dc3  mov     ecx, eax; SecStatus
0x140069dc5  call    cs:__imp_MapSecurityError
0x140069dcc  nop     dword ptr [rax+rax+00h]
0x140069dd1  mov     ebx, eax
0x140069dd3  test    eax, eax
0x140069dd5  jns     short loc_140069E1B
0x140069dd7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140069dde  lea     r14, WPP_GLOBAL_Control
0x140069de5  cmp     rcx, r14
0x140069de8  jz      loc_140069FE6
0x140069dee  bt      dword ptr [rcx+2Ch], 11h
0x140069df3  jnb     loc_140069FE6
0x140069df9  cmp     byte ptr [rcx+29h], 2
0x140069dfd  jb      loc_140069FE6
0x140069e03  mov     rcx, [rcx+18h]
0x140069e07  lea     edx, [rsi+32h]
0x140069e0a  lea     r8, WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids
0x140069e11  call    WPP_SF_
0x140069e16  jmp     loc_140069FE6
0x140069e1b  mov     rdx, [rbp+pBuffer]; SourceString
0x140069e1f  test    rdx, rdx
0x140069e22  jz      loc_140069EAB
0x140069e28  cmp     [rdx], r12w
0x140069e2c  jz      short loc_140069EAB
0x140069e2e  lea     rcx, [rbp+DestinationString]; DestinationString
0x140069e32  call    cs:__imp_RtlInitUnicodeString
0x140069e39  nop     dword ptr [rax+rax+00h]
0x140069e3e  movzx   edx, [rbp+DestinationString.Length]
0x140069e42  mov     ecx, r12d
0x140069e45  mov     r8, [rbp+DestinationString.Buffer]
0x140069e49  movzx   r9d, dx
0x140069e4d  shr     r9w, 1
0x140069e51  mov     [rbp+var_18], r8
0x140069e55  cmp     r12w, r9w
0x140069e59  jnb     short loc_140069E6F
0x140069e5b  movzx   eax, cx
0x140069e5e  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x140069e64  jz      short loc_140069E6F
0x140069e66  add     cx, si
0x140069e69  cmp     cx, r9w
0x140069e6d  jb      short loc_140069E5B
0x140069e6f  movzx   eax, cx
0x140069e72  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x140069e78  jnz     short loc_140069EA1
0x140069e7a  add     cx, cx
0x140069e7d  inc     rax
0x140069e80  sub     dx, cx
0x140069e83  mov     word ptr [rbp+var_20], cx
0x140069e87  mov     word ptr [rbp+var_20+2], cx
0x140069e8b  sub     dx, 2
0x140069e8f  lea     rax, [r8+rax*2]
0x140069e93  mov     [rbp+var_28], rax
0x140069e97  mov     word ptr [rbp+var_30], dx
0x140069e9b  mov     word ptr [rbp+var_30+2], dx
0x140069e9f  jmp     short loc_140069EB5
0x140069ea1  mov     dword ptr [rbp+var_20], r12d
0x140069ea5  mov     [rbp+var_28], r8
0x140069ea9  jmp     short loc_140069E97
0x140069eab  mov     word ptr [rbp+var_30], r12w
0x140069eb0  mov     word ptr [rbp+var_20], r12w
0x140069eb5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140069ebc  lea     r14, WPP_GLOBAL_Control
0x140069ec3  cmp     rcx, r14
0x140069ec6  jz      short loc_140069EF7
0x140069ec8  bt      dword ptr [rcx+2Ch], 11h
0x140069ecd  jnb     short loc_140069EF7
0x140069ecf  cmp     byte ptr [rcx+29h], 4
0x140069ed3  jb      short loc_140069EF7
0x140069ed5  mov     rcx, [rcx+18h]
0x140069ed9  lea     rax, [rbp+var_30]
0x140069edd  mov     edx, 34h ; '4'
0x140069ee2  mov     [rsp+70h+var_50], rax
0x140069ee7  lea     r9, [rbp+var_20]
0x140069eeb  lea     r8, WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids
0x140069ef2  call    WPP_SF_ZZ
0x140069ef7  mov     rcx, cs:Smb2S4U2SelfContext
0x140069efe  lea     r9, [rbp+ThreadInformation]
0x140069f02  lea     r8, [rbp+var_20]
0x140069f06  lea     rdx, [rbp+var_30]
0x140069f0a  call    cs:__imp_SrvLibS4U2SelfAuth
0x140069f11  nop     dword ptr [rax+rax+00h]
0x140069f16  mov     ebx, eax
0x140069f18  test    eax, eax
0x140069f1a  js      loc_140069FB5
0x140069f20  mov     r9d, 8; ThreadInformationLength
0x140069f26  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x140069f2a  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x140069f31  lea     edx, [r9-3]; ThreadInformationClass
0x140069f35  call    cs:__imp_NtSetInformationThread
0x140069f3c  nop     dword ptr [rax+rax+00h]
0x140069f41  mov     ebx, eax
0x140069f43  test    eax, eax
0x140069f45  js      short loc_140069F7E
0x140069f47  mov     rcx, rdi
0x140069f4a  call    Smb2SecurityContextCaptureThreadToken
0x140069f4f  cmp     [rdi+18h], r12b
0x140069f53  jz      short loc_140069F77
0x140069f55  mov     rcx, [rdi+30h]; Token
0x140069f59  test    rcx, rcx
0x140069f5c  jz      short loc_140069F77
0x140069f5e  mov     rdx, [r15+20h]
0x140069f62  add     rdx, 0A0h; AuthenticationId
0x140069f69  call    cs:__imp_SeQueryAuthenticationIdToken
0x140069f70  nop     dword ptr [rax+rax+00h]
0x140069f75  mov     ebx, eax
0x140069f77  call    Smb2Revert
0x140069f7c  jmp     short loc_140069FAF
0x140069f7e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140069f85  cmp     rcx, r14
0x140069f88  jz      short loc_140069FAF
0x140069f8a  bt      dword ptr [rcx+2Ch], 11h
0x140069f8f  jnb     short loc_140069FAF
0x140069f91  cmp     [rcx+29h], sil
0x140069f95  jb      short loc_140069FAF
0x140069f97  mov     rcx, [rcx+18h]
0x140069f9b  lea     r8, WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids
0x140069fa2  mov     edx, 35h ; '5'
0x140069fa7  mov     r9d, eax
0x140069faa  call    WPP_SF_d
0x140069faf  test    ebx, ebx
0x140069fb1  js      short loc_140069FE6
0x140069fb3  jmp     short loc_14006A026
0x140069fb5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140069fbc  cmp     rcx, r14
0x140069fbf  jz      short loc_140069FE6
0x140069fc1  bt      dword ptr [rcx+2Ch], 11h
0x140069fc6  jnb     short loc_140069FE6
0x140069fc8  cmp     [rcx+29h], sil
0x140069fcc  jb      short loc_140069FE6
0x140069fce  mov     rcx, [rcx+18h]
0x140069fd2  lea     r8, WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids
0x140069fd9  mov     edx, 36h ; '6'
0x140069fde  mov     r9d, eax
0x140069fe1  call    WPP_SF_d
0x140069fe6  test    cs:byte_14004C339, 40h
0x140069fed  jz      short loc_14006A026
0x140069fef  mov     rax, [rbp+var_18]
0x140069ff3  lea     r8, [r13+248h]
0x140069ffa  movzx   ecx, word ptr [rbp+var_20]
0x140069ffe  movzx   r9d, word ptr [rbp+var_30]
0x14006a003  mov     [rsp+70h+var_38], ebx
0x14006a007  mov     [rsp+70h+var_40], rax
0x14006a00c  mov     rax, [rbp+var_28]
0x14006a010  shr     cx, 1
0x14006a013  mov     [rsp+70h+var_48], cx
0x14006a018  shr     r9w, 1
0x14006a01c  mov     [rsp+70h+var_50], rax
0x14006a021  call    McTemplateK0hzr0hzr2q_EtwWriteTransfer
0x14006a026  mov     rcx, [rbp+pBuffer]; pvContextBuffer
0x14006a02a  test    rcx, rcx
0x14006a02d  jz      short loc_14006A03B
0x14006a02f  call    cs:__imp_FreeContextBuffer
0x14006a036  nop     dword ptr [rax+rax+00h]
0x14006a03b  mov     rcx, [rbp+ThreadInformation]; Handle
0x14006a03f  test    rcx, rcx
0x14006a042  jz      short loc_14006A050
0x14006a044  call    cs:__imp_NtClose
0x14006a04b  nop     dword ptr [rax+rax+00h]
0x14006a050  mov     eax, ebx
0x14006a052  jmp     short loc_14006A059
0x14006a054  mov     eax, 0C0000008h
0x14006a059  mov     rbx, [rsp+70h+arg_10]
0x14006a061  add     rsp, 70h
0x14006a065  pop     r15
0x14006a067  pop     r14
0x14006a069  pop     r13
0x14006a06b  pop     r12
0x14006a06d  pop     rdi
0x14006a06e  pop     rsi
0x14006a06f  pop     rbp
0x14006a070  retn
```
