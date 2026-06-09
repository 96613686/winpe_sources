# MpCreateNriServiceSID

- ea: `0x140093168`
- end: `0x140093352`
- name: `MpCreateNriServiceSID`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callers

- `0x1400907b8`

## callees

- `0x1400026c0`
- `0x1400051bc`
- `0x1400118d0`
- `0x140080070`
- `0x140093168`

## import_xrefs

- `ntoskrnl!RtlInitializeSid` at `0x14009322c`
- `ntoskrnl!RtlInitializeSid` at `0x14009322c`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140093299`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400932b3`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400932cd`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400932e7`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140093301`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14009331b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140093299`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400932b3`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400932cd`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400932e7`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140093301`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14009331b`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400931a4`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400931a4`

## pseudocode

```c
__int64 __fastcall MpCreateNriServiceSID(_QWORD *a1)
{
  ULONG v2; // eax
  void *PoolWithTag; // rax
  void *v4; // rdi
  NTSTATUS v5; // ebx
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+30h] [rbp-18h] BYREF

  *a1 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v2 = RtlLengthRequiredSid(6u);
  PoolWithTag = (void *)MpAllocatePoolWithTag(1, v2, 1685278797);
  v4 = PoolWithTag;
  if ( PoolWithTag )
  {
    v5 = RtlInitializeSid(PoolWithTag, &IdentifierAuthority, 6u);
    if ( v5 >= 0 )
    {
      _mm_lfence();
      *RtlSubAuthoritySid(v4, 0) = 80;
      *RtlSubAuthoritySid(v4, 1u) = -626156335;
      *RtlSubAuthoritySid(v4, 2u) = -1826242828;
      *RtlSubAuthoritySid(v4, 3u) = -210382986;
      *RtlSubAuthoritySid(v4, 4u) = -1265745923;
      v5 = 0;
      *RtlSubAuthoritySid(v4, 5u) = 430494444;
      *a1 = v4;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          26,
          WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids,
          KeGetCurrentThread(),
          v5);
      }
      MpFreeServiceSID(v4);
    }
  }
  else
  {
    v5 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        25,
        WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids,
        KeGetCurrentThread(),
        -1073741670);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140093168  mov     [rsp+arg_8], rbx
0x14009316d  mov     [rsp+arg_10], rsi
0x140093172  push    rdi
0x140093173  sub     rsp, 40h
0x140093177  mov     rax, cs:__security_cookie
0x14009317e  xor     rax, rsp
0x140093181  mov     [rsp+48h+var_10], rax
0x140093186  mov     rsi, rcx
0x140093189  mov     qword ptr [rcx], 0
0x140093190  mov     ecx, 6; SubAuthorityCount
0x140093195  mov     dword ptr [rsp+48h+IdentifierAuthority.Value], 0
0x14009319d  mov     word ptr [rsp+48h+IdentifierAuthority.Value+4], 500h
0x1400931a4  call    cs:__imp_RtlLengthRequiredSid
0x1400931ab  nop     dword ptr [rax+rax+00h]
0x1400931b0  mov     edx, eax
0x1400931b2  mov     ecx, 1
0x1400931b7  mov     r8d, 6473504Dh
0x1400931bd  call    MpAllocatePoolWithTag
0x1400931c2  mov     rdi, rax
0x1400931c5  test    rax, rax
0x1400931c8  jnz     short loc_140093221
0x1400931ca  mov     ebx, 0C000009Ah
0x1400931cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400931d6  lea     rax, WPP_GLOBAL_Control
0x1400931dd  cmp     rcx, rax
0x1400931e0  jz      loc_140093332
0x1400931e6  mov     eax, [rcx+2Ch]
0x1400931e9  test    al, 1
0x1400931eb  jz      loc_140093332
0x1400931f1  mov     r9, gs:188h
0x1400931fa  lea     edx, [rdi+19h]
0x1400931fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140093204  lea     r8, WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids
0x14009320b  mov     [rsp+48h+var_28], 0C000009Ah
0x140093213  mov     rcx, [rcx+18h]
0x140093217  call    WPP_SF_qD
0x14009321c  jmp     loc_140093332
0x140093221  mov     r8b, 6; SubAuthorityCount
0x140093224  lea     rdx, [rsp+48h+IdentifierAuthority]; IdentifierAuthority
0x140093229  mov     rcx, rdi; Sid
0x14009322c  call    cs:__imp_RtlInitializeSid
0x140093233  nop     dword ptr [rax+rax+00h]
0x140093238  mov     ebx, eax
0x14009323a  test    eax, eax
0x14009323c  jns     short loc_140093291
0x14009323e  mov     rcx, cs:WPP_GLOBAL_Control
0x140093245  lea     rax, WPP_GLOBAL_Control
0x14009324c  cmp     rcx, rax
0x14009324f  jz      short loc_140093284
0x140093251  mov     eax, [rcx+2Ch]
0x140093254  test    al, 1
0x140093256  jz      short loc_140093284
0x140093258  lfence
0x14009325b  mov     r9, gs:188h
0x140093264  lea     r8, WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids
0x14009326b  mov     rcx, cs:WPP_GLOBAL_Control
0x140093272  mov     edx, 1Ah
0x140093277  mov     [rsp+48h+var_28], ebx
0x14009327b  mov     rcx, [rcx+18h]
0x14009327f  call    WPP_SF_qD
0x140093284  mov     rcx, rdi
0x140093287  call    MpFreeServiceSID
0x14009328c  jmp     loc_140093332
0x140093291  lfence
0x140093294  xor     edx, edx; SubAuthority
0x140093296  mov     rcx, rdi; Sid
0x140093299  call    cs:__imp_RtlSubAuthoritySid
0x1400932a0  nop     dword ptr [rax+rax+00h]
0x1400932a5  mov     edx, 1; SubAuthority
0x1400932aa  mov     rcx, rdi; Sid
0x1400932ad  mov     dword ptr [rax], 50h ; 'P'
0x1400932b3  call    cs:__imp_RtlSubAuthoritySid
0x1400932ba  nop     dword ptr [rax+rax+00h]
0x1400932bf  mov     edx, 2; SubAuthority
0x1400932c4  mov     rcx, rdi; Sid
0x1400932c7  mov     dword ptr [rax], 0DAAD9CD1h
0x1400932cd  call    cs:__imp_RtlSubAuthoritySid
0x1400932d4  nop     dword ptr [rax+rax+00h]
0x1400932d9  mov     edx, 3; SubAuthority
0x1400932de  mov     rcx, rdi; Sid
0x1400932e1  mov     dword ptr [rax], 9325BEF4h
0x1400932e7  call    cs:__imp_RtlSubAuthoritySid
0x1400932ee  nop     dword ptr [rax+rax+00h]
0x1400932f3  mov     edx, 4; SubAuthority
0x1400932f8  mov     rcx, rdi; Sid
0x1400932fb  mov     dword ptr [rax], 0F375CF76h
0x140093301  call    cs:__imp_RtlSubAuthoritySid
0x140093308  nop     dword ptr [rax+rax+00h]
0x14009330d  mov     edx, 5; SubAuthority
0x140093312  mov     rcx, rdi; Sid
0x140093315  mov     dword ptr [rax], 0B48E3FFDh
0x14009331b  call    cs:__imp_RtlSubAuthoritySid
0x140093322  nop     dword ptr [rax+rax+00h]
0x140093327  xor     ebx, ebx
0x140093329  mov     dword ptr [rax], 19A8D2ECh
0x14009332f  mov     [rsi], rdi
0x140093332  mov     eax, ebx
0x140093334  mov     rcx, [rsp+48h+var_10]
0x140093339  xor     rcx, rsp; StackCookie
0x14009333c  call    __security_check_cookie
0x140093341  mov     rbx, [rsp+48h+arg_8]
0x140093346  mov     rsi, [rsp+48h+arg_10]
0x14009334b  add     rsp, 40h
0x14009334f  pop     rdi
0x140093350  retn
```
