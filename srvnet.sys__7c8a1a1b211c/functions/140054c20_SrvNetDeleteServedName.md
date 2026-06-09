# SrvNetDeleteServedName

- ea: `0x140054c20`
- end: `0x140054f9e`
- name: `SrvNetDeleteServedName`
- size: `894`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1400079a0`
- `0x140008bb0`
- `0x140055720`

## callees

- `0x140008820`
- `0x14000b480`
- `0x14000ec20`
- `0x1400105e0`
- `0x1400163d8`
- `0x14001f728`
- `0x14002a3e0`
- `0x140054c20`
- `0x140055fd0`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x140054e27`
- `ntoskrnl!ExReleaseFastMutex` at `0x140054e27`
- `ntoskrnl!KeStackAttachProcess` at `0x140054c9d`
- `ntoskrnl!KeStackAttachProcess` at `0x140054c9d`
- `ntoskrnl!ExAcquireFastMutex` at `0x140054dff`
- `ntoskrnl!ExAcquireFastMutex` at `0x140054dff`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140054f64`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140054f64`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140054d62`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140054d85`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140054d62`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140054d85`
- `ntoskrnl!IoGetCurrentProcess` at `0x140054c84`
- `ntoskrnl!IoGetCurrentProcess` at `0x140054c84`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140054d22`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140054e57`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140054d22`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140054e57`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140054dd9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140054ea0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140054dd9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140054ea0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140054d06`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140054e3b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140054d06`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140054e3b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140054dcd`
- `ntoskrnl!ExReleaseResourceLite` at `0x140054e94`
- `ntoskrnl!ExReleaseResourceLite` at `0x140054dcd`
- `ntoskrnl!ExReleaseResourceLite` at `0x140054e94`

## pseudocode

```c
__int64 __fastcall SrvNetDeleteServedName(unsigned __int16 *a1, unsigned __int16 *a2, const UNICODE_STRING *a3)
{
  int v6; // ebp
  char v7; // r12
  struct _KPROCESS *v8; // rbx
  PERESOURCE v9; // rcx
  PVOID *p_Reserved2; // rax
  PVOID *Reserved2; // rbx
  const UNICODE_STRING *v12; // rdi
  PVOID v13; // rcx
  __int64 Buffer; // rax
  int Length; // edx
  __int64 v16; // r10
  int v17; // ecx
  __int64 v18; // r8
  int v19; // r9d
  __int128 v21; // [rsp+50h] [rbp-88h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+60h] [rbp-78h] BYREF

  memset(&ApcState, 0, sizeof(ApcState));
  v21 = 0;
  v6 = -1073741772;
  v7 = 0;
  v8 = *(struct _KPROCESS **)&SrvNetDeviceExtension[4].ActiveCount;
  if ( IoGetCurrentProcess() != v8 )
  {
    KeStackAttachProcess(v8, &ApcState);
    v7 = 1;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_8d73355e5e233ce540e4603b97b45138_Traceguids, a1);
  }
  if ( a1 )
  {
    v21 = *(_OWORD *)a1;
    SrvNetStripEndpointName(&v21);
  }
  else
  {
    LOWORD(v21) = 0;
  }
  KeEnterCriticalRegion();
  ExAcquireResourceSharedLite((PERESOURCE)((char *)SrvNetDeviceExtension + 288), 1u);
  v9 = SrvNetDeviceExtension;
  p_Reserved2 = &SrvNetDeviceExtension[3].Reserved2;
  Reserved2 = (PVOID *)SrvNetDeviceExtension[3].Reserved2;
  while ( Reserved2 != p_Reserved2 )
  {
    v12 = (const UNICODE_STRING *)&v21;
    if ( !(_WORD)v21 )
      v12 = 0;
    if ( a3 && !RtlEqualUnicodeString(a3, (PCUNICODE_STRING)(Reserved2 + 9), 1u)
      || v12 && !RtlEqualUnicodeString(v12, (PCUNICODE_STRING)(Reserved2 + 11), 1u)
      || *((_BYTE *)Reserved2 + 120) )
    {
      Reserved2 = (PVOID *)*Reserved2;
    }
    else
    {
      SrvNetReferenceEndpoint(Reserved2);
      v13 = Reserved2[46];
      if ( v13 )
        SrvNetReferenceListenerRuleEntry(v13);
      v6 = 0;
      ExReleaseResourceLite((PERESOURCE)((char *)SrvNetDeviceExtension + 288));
      KeLeaveCriticalRegion();
      if ( !*((_BYTE *)Reserved2 + 120) )
      {
        if ( *((_BYTE *)Reserved2 + 121) )
          ExAcquireFastMutex((PFAST_MUTEX)&SrvNetDeviceExtension[2].ActiveCount);
        SrvNetCloseEndpoint((__int64 *)Reserved2);
        if ( *((_BYTE *)Reserved2 + 121) )
          ExReleaseFastMutex((PFAST_MUTEX)&SrvNetDeviceExtension[2].ActiveCount);
      }
      SrvNetDereferenceEndpoint(Reserved2);
      KeEnterCriticalRegion();
      ExAcquireResourceSharedLite((PERESOURCE)((char *)SrvNetDeviceExtension + 288), 1u);
      Reserved2 = (PVOID *)SrvNetDeviceExtension[3].Reserved2;
    }
    v9 = SrvNetDeviceExtension;
    p_Reserved2 = &SrvNetDeviceExtension[3].Reserved2;
  }
  ExReleaseResourceLite((PERESOURCE)((char *)v9 + 288));
  KeLeaveCriticalRegion();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_8d73355e5e233ce540e4603b97b45138_Traceguids, a1);
  }
  if ( v6 >= 0 && (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x1000) != 0 )
  {
    if ( a3 )
    {
      Length = a3->Length;
      Buffer = (__int64)a3->Buffer;
      LOWORD(Length) = (unsigned __int16)Length >> 1;
    }
    else
    {
      Length = 0;
      Buffer = 0;
    }
    if ( a2 )
    {
      v17 = *a2;
      v16 = *((_QWORD *)a2 + 1);
      LOWORD(v17) = (unsigned __int16)v17 >> 1;
    }
    else
    {
      v17 = 0;
      v16 = 0;
    }
    if ( a1 )
    {
      v19 = *a1;
      v18 = *((_QWORD *)a1 + 1);
      LOWORD(v19) = (unsigned __int16)v19 >> 1;
    }
    else
    {
      v19 = 0;
      v18 = 0;
    }
    McTemplateK0hzr0hzr2hzr4_EtwWriteTransfer(v17, Length, v18, v19, v18, v17, v16, Length, Buffer);
  }
  if ( v7 )
    KeUnstackDetachProcess(&ApcState);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140054c20  mov     r11, rsp
0x140054c23  mov     [r11+20h], rbx
0x140054c27  push    rbp
0x140054c28  push    rsi
0x140054c29  push    rdi
0x140054c2a  push    r12
0x140054c2c  push    r13
0x140054c2e  push    r14
0x140054c30  push    r15
0x140054c32  sub     rsp, 0A0h
0x140054c39  mov     rax, cs:__security_cookie
0x140054c40  xor     rax, rsp
0x140054c43  mov     [rsp+0D8h+var_48], rax
0x140054c4b  mov     rax, cs:SrvNetDeviceExtension
0x140054c52  xorps   xmm0, xmm0
0x140054c55  movups  xmmword ptr [rsp+0D8h+ApcState.ApcListHead.Flink], xmm0
0x140054c5a  xor     r13d, r13d
0x140054c5d  mov     r14, r8
0x140054c60  movups  xmmword ptr [rsp+0D8h+ApcState.ApcListHead.Flink+10h], xmm0
0x140054c65  mov     r15, rdx
0x140054c68  mov     rsi, rcx
0x140054c6b  movups  [rsp+0D8h+var_88], xmm0
0x140054c70  mov     ebp, 0C0000034h
0x140054c75  mov     r12b, r13b
0x140054c78  movups  xmmword ptr [r11-58h], xmm0
0x140054c7d  mov     rbx, [rax+1B8h]
0x140054c84  call    cs:__imp_IoGetCurrentProcess
0x140054c8b  nop     dword ptr [rax+rax+00h]
0x140054c90  cmp     rax, rbx
0x140054c93  jz      short loc_140054CAC
0x140054c95  lea     rdx, [rsp+0D8h+ApcState]; ApcState
0x140054c9a  mov     rcx, rbx; PROCESS
0x140054c9d  call    cs:__imp_KeStackAttachProcess
0x140054ca4  nop     dword ptr [rax+rax+00h]
0x140054ca9  mov     r12b, 1
0x140054cac  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140054cb3  lea     rax, WPP_GLOBAL_Control
0x140054cba  cmp     rcx, rax
0x140054cbd  jz      short loc_140054CE6
0x140054cbf  test    dword ptr [rcx+2Ch], 100h
0x140054cc6  jz      short loc_140054CE6
0x140054cc8  cmp     byte ptr [rcx+29h], 2
0x140054ccc  jb      short loc_140054CE6
0x140054cce  mov     rcx, [rcx+18h]
0x140054cd2  lea     r8, WPP_8d73355e5e233ce540e4603b97b45138_Traceguids
0x140054cd9  mov     edx, 2Eh ; '.'
0x140054cde  mov     r9, rsi
0x140054ce1  call    WPP_SF_Z
0x140054ce6  test    rsi, rsi
0x140054ce9  jz      short loc_140054D00
0x140054ceb  movups  xmm0, xmmword ptr [rsi]
0x140054cee  lea     rcx, [rsp+0D8h+var_88]
0x140054cf3  movdqu  [rsp+0D8h+var_88], xmm0
0x140054cf9  call    SrvNetStripEndpointName
0x140054cfe  jmp     short loc_140054D06
0x140054d00  mov     word ptr [rsp+0D8h+var_88], r13w
0x140054d06  call    cs:__imp_KeEnterCriticalRegion
0x140054d0d  nop     dword ptr [rax+rax+00h]
0x140054d12  mov     rcx, cs:SrvNetDeviceExtension
0x140054d19  mov     dl, 1; Wait
0x140054d1b  add     rcx, 120h; Resource
0x140054d22  call    cs:__imp_ExAcquireResourceSharedLite
0x140054d29  nop     dword ptr [rax+rax+00h]
0x140054d2e  mov     rcx, cs:SrvNetDeviceExtension
0x140054d35  lea     rax, [rcx+188h]
0x140054d3c  mov     rbx, [rax]
0x140054d3f  jmp     loc_140054E84
0x140054d44  cmp     word ptr [rsp+0D8h+var_88], r13w
0x140054d4a  lea     rdi, [rsp+0D8h+var_88]
0x140054d4f  cmovbe  rdi, r13
0x140054d53  test    r14, r14
0x140054d56  jz      short loc_140054D76
0x140054d58  lea     rdx, [rbx+48h]; String2
0x140054d5c  mov     r8b, 1; CaseInSensitive
0x140054d5f  mov     rcx, r14; String1
0x140054d62  call    cs:__imp_RtlEqualUnicodeString
0x140054d69  nop     dword ptr [rax+rax+00h]
0x140054d6e  test    al, al
0x140054d70  jz      loc_140054E73
0x140054d76  test    rdi, rdi
0x140054d79  jz      short loc_140054D99
0x140054d7b  lea     rdx, [rbx+58h]; String2
0x140054d7f  mov     r8b, 1; CaseInSensitive
0x140054d82  mov     rcx, rdi; String1
0x140054d85  call    cs:__imp_RtlEqualUnicodeString
0x140054d8c  nop     dword ptr [rax+rax+00h]
0x140054d91  test    al, al
0x140054d93  jz      loc_140054E73
0x140054d99  cmp     [rbx+78h], r13b
0x140054d9d  jnz     loc_140054E73
0x140054da3  mov     rcx, rbx
0x140054da6  call    SrvNetReferenceEndpoint
0x140054dab  mov     rcx, [rbx+170h]
0x140054db2  test    rcx, rcx
0x140054db5  jz      short loc_140054DBC
0x140054db7  call    SrvNetReferenceListenerRuleEntry
0x140054dbc  mov     rcx, cs:SrvNetDeviceExtension
0x140054dc3  mov     ebp, r13d
0x140054dc6  add     rcx, 120h; Resource
0x140054dcd  call    cs:__imp_ExReleaseResourceLite
0x140054dd4  nop     dword ptr [rax+rax+00h]
0x140054dd9  call    cs:__imp_KeLeaveCriticalRegion
0x140054de0  nop     dword ptr [rax+rax+00h]
0x140054de5  cmp     [rbx+78h], r13b
0x140054de9  jnz     short loc_140054E33
0x140054deb  cmp     [rbx+79h], r13b
0x140054def  jz      short loc_140054E0B
0x140054df1  mov     rcx, cs:SrvNetDeviceExtension
0x140054df8  add     rcx, 0E8h; FastMutex
0x140054dff  call    cs:__imp_ExAcquireFastMutex
0x140054e06  nop     dword ptr [rax+rax+00h]
0x140054e0b  mov     rcx, rbx
0x140054e0e  call    SrvNetCloseEndpoint
0x140054e13  cmp     [rbx+79h], r13b
0x140054e17  jz      short loc_140054E33
0x140054e19  mov     rcx, cs:SrvNetDeviceExtension
0x140054e20  add     rcx, 0E8h; FastMutex
0x140054e27  call    cs:__imp_ExReleaseFastMutex
0x140054e2e  nop     dword ptr [rax+rax+00h]
0x140054e33  mov     rcx, rbx
0x140054e36  call    SrvNetDereferenceEndpoint
0x140054e3b  call    cs:__imp_KeEnterCriticalRegion
0x140054e42  nop     dword ptr [rax+rax+00h]
0x140054e47  mov     rcx, cs:SrvNetDeviceExtension
0x140054e4e  mov     dl, 1; Wait
0x140054e50  add     rcx, 120h; Resource
0x140054e57  call    cs:__imp_ExAcquireResourceSharedLite
0x140054e5e  nop     dword ptr [rax+rax+00h]
0x140054e63  mov     rax, cs:SrvNetDeviceExtension
0x140054e6a  mov     rbx, [rax+188h]
0x140054e71  jmp     short loc_140054E76
0x140054e73  mov     rbx, [rbx]
0x140054e76  mov     rcx, cs:SrvNetDeviceExtension
0x140054e7d  lea     rax, [rcx+188h]
0x140054e84  cmp     rbx, rax
0x140054e87  jnz     loc_140054D44
0x140054e8d  add     rcx, 120h; Resource
0x140054e94  call    cs:__imp_ExReleaseResourceLite
0x140054e9b  nop     dword ptr [rax+rax+00h]
0x140054ea0  call    cs:__imp_KeLeaveCriticalRegion
0x140054ea7  nop     dword ptr [rax+rax+00h]
0x140054eac  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140054eb3  lea     rax, WPP_GLOBAL_Control
0x140054eba  cmp     rcx, rax
0x140054ebd  jz      short loc_140054EE6
0x140054ebf  test    dword ptr [rcx+2Ch], 100h
0x140054ec6  jz      short loc_140054EE6
0x140054ec8  cmp     byte ptr [rcx+29h], 2
0x140054ecc  jb      short loc_140054EE6
0x140054ece  mov     rcx, [rcx+18h]
0x140054ed2  lea     r8, WPP_8d73355e5e233ce540e4603b97b45138_Traceguids
0x140054ed9  mov     edx, 2Fh ; '/'
0x140054ede  mov     r9, rsi
0x140054ee1  call    WPP_SF_Z
0x140054ee6  test    ebp, ebp
0x140054ee8  js      short loc_140054F5A
0x140054eea  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 10h
0x140054ef1  jz      short loc_140054F5A
0x140054ef3  test    r14, r14
0x140054ef6  jz      short loc_140054F05
0x140054ef8  movzx   edx, word ptr [r14]
0x140054efc  mov     rax, [r14+8]
0x140054f00  shr     dx, 1
0x140054f03  jmp     short loc_140054F0B
0x140054f05  mov     edx, r13d
0x140054f08  mov     rax, r13
0x140054f0b  test    r15, r15
0x140054f0e  jz      short loc_140054F1D
0x140054f10  movzx   ecx, word ptr [r15]
0x140054f14  mov     r10, [r15+8]
0x140054f18  shr     cx, 1
0x140054f1b  jmp     short loc_140054F23
0x140054f1d  mov     ecx, r13d
0x140054f20  mov     r10, r13
0x140054f23  test    rsi, rsi
0x140054f26  jz      short loc_140054F36
0x140054f28  movzx   r9d, word ptr [rsi]
0x140054f2c  mov     r8, [rsi+8]
0x140054f30  shr     r9w, 1
0x140054f34  jmp     short loc_140054F3C
0x140054f36  mov     r9d, r13d
0x140054f39  mov     r8, r13
0x140054f3c  mov     [rsp+0D8h+var_98], rax
0x140054f41  mov     [rsp+0D8h+var_A0], dx
0x140054f46  mov     [rsp+0D8h+var_A8], r10
0x140054f4b  mov     [rsp+0D8h+var_B0], cx
0x140054f50  mov     [rsp+0D8h+var_B8], r8
0x140054f55  call    McTemplateK0hzr0hzr2hzr4_EtwWriteTransfer
0x140054f5a  test    r12b, r12b
0x140054f5d  jz      short loc_140054F70
0x140054f5f  lea     rcx, [rsp+0D8h+ApcState]; ApcState
0x140054f64  call    cs:__imp_KeUnstackDetachProcess
0x140054f6b  nop     dword ptr [rax+rax+00h]
0x140054f70  mov     eax, ebp
0x140054f72  mov     rcx, [rsp+0D8h+var_48]
0x140054f7a  xor     rcx, rsp; StackCookie
0x140054f7d  call    __security_check_cookie
0x140054f82  mov     rbx, [rsp+0D8h+arg_18]
0x140054f8a  add     rsp, 0A0h
0x140054f91  pop     r15
0x140054f93  pop     r14
0x140054f95  pop     r13
0x140054f97  pop     r12
0x140054f99  pop     rdi
0x140054f9a  pop     rsi
0x140054f9b  pop     rbp
0x140054f9c  retn
```
