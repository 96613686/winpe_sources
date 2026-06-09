# Sid::Sid(void)

- ea: `0x14008273c`
- end: `0x1400827e1`
- name: `??0Sid@@QEAA@XZ`
- size: `165`
- prototype: `Sid *__fastcall(Sid *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14002f5b8`
- `0x1400829f4`
- `0x1400833f8`

## callees

- `0x140006314`
- `0x14001f6b4`
- `0x14008273c`

## import_xrefs

- `ADVAPI32!CreateWellKnownSid` at `0x140082776`
- `ADVAPI32!CreateWellKnownSid` at `0x140082776`
- `KERNEL32!GetLastError` at `0x140082799`
- `KERNEL32!GetLastError` at `0x140082799`

## pseudocode

```c
Sid *__fastcall Sid::Sid(Sid *this)
{
  signed int LastError; // eax
  DWORD cbSid; // [rsp+30h] [rbp+8h] BYREF

  cbSid = 68;
  *(_OWORD *)((char *)this + 72) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 7;
  *((_WORD *)this + 36) = 0;
  if ( !CreateWellKnownSid(WinNullSid, 0, this, &cbSid) )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        23,
        WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids,
        (unsigned int)LastError);
    }
    memset_0(this, 0, 0x44u);
  }
  return this;
}

```

## disassembly

```asm
0x14008273c  push    rbx
0x14008273e  sub     rsp, 20h
0x140082742  xorps   xmm0, xmm0
0x140082745  mov     [rsp+28h+cbSid], 44h ; 'D'
0x14008274d  movups  xmmword ptr [rcx+48h], xmm0
0x140082751  mov     qword ptr [rcx+58h], 0
0x140082759  lea     r9, [rsp+28h+cbSid]; cbSid
0x14008275e  mov     qword ptr [rcx+60h], 7
0x140082766  xor     eax, eax
0x140082768  mov     [rcx+48h], ax
0x14008276c  mov     rbx, rcx
0x14008276f  mov     r8, rcx; pSid
0x140082772  xor     edx, edx; DomainSid
0x140082774  xor     ecx, ecx; WellKnownSidType
0x140082776  call    cs:__imp_CreateWellKnownSid
0x14008277c  test    eax, eax
0x14008277e  jnz     short loc_1400827D8
0x140082780  mov     rax, cs:WPP_GLOBAL_Control
0x140082787  lea     rcx, WPP_GLOBAL_Control
0x14008278e  cmp     rax, rcx
0x140082791  jz      short loc_1400827CA
0x140082793  test    byte ptr [rax+1Ch], 1
0x140082797  jz      short loc_1400827CA
0x140082799  call    cs:__imp_GetLastError
0x14008279f  test    eax, eax
0x1400827a1  jle     short loc_1400827AB
0x1400827a3  movzx   eax, ax
0x1400827a6  or      eax, 80070000h
0x1400827ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400827b2  lea     r8, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids
0x1400827b9  mov     edx, 17h
0x1400827be  mov     r9d, eax
0x1400827c1  mov     rcx, [rcx+10h]
0x1400827c5  call    WPP_SF_d
0x1400827ca  xor     edx, edx; Val
0x1400827cc  mov     rcx, rbx; void *
0x1400827cf  lea     r8d, [rdx+44h]; Size
0x1400827d3  call    memset_0
0x1400827d8  mov     rax, rbx
0x1400827db  add     rsp, 20h
0x1400827df  pop     rbx
0x1400827e0  retn
```
