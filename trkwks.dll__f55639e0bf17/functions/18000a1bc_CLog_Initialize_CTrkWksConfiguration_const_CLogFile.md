# CLog::Initialize(CTrkWksConfiguration const *,CLogFile *)

- ea: `0x18000a1bc`
- end: `0x18000a276`
- name: `?Initialize@CLog@@QEAAXPEBVCTrkWksConfiguration@@PEAVCLogFile@@@Z`
- size: `186`
- prototype: `void __fastcall(CLog *this, const struct CTrkWksConfiguration *, struct CLogFile *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000756c`

## callees

- `0x1800087c0`
- `0x18000a1bc`
- `0x18000cf34`
- `0x18000cf58`
- `0x180011000`

## pseudocode

```c
void __fastcall CLog::Initialize(CLog *this, const struct CTrkWksConfiguration *a2, struct CLogFile *a3)
{
  CLogFile *v3; // rax
  __int128 v5; // xmm1
  _OWORD *LogInfo; // rax
  _BYTE v7[32]; // [rsp+20h] [rbp-58h] BYREF
  _OWORD v8[2]; // [rsp+40h] [rbp-38h] BYREF

  v3 = a3;
  memset(v8, 0, 28);
  if ( a3 )
    *((_QWORD *)this + 1) = a3;
  else
    v3 = (CLogFile *)*((_QWORD *)this + 1);
  if ( a2 )
    *((_QWORD *)this + 6) = a2;
  CLogFile::ReadExtendedHeader(v3, 0x40u, v8, 0x1Cu);
  if ( !(unsigned int)CLogFileHeader::IsShutdown((CLogFileHeader *)(*((_QWORD *)this + 1) + 80LL))
    || LODWORD(v8[0]) == DWORD1(v8[0]) )
  {
    *(_DWORD *)this |= 1u;
    LogInfo = (_OWORD *)CLog::QueryLogInfo(this, v7);
    v5 = *(_OWORD *)((char *)LogInfo + 12);
    v8[0] = *LogInfo;
    *(_OWORD *)((char *)v8 + 12) = v5;
  }
  else
  {
    v5 = *(_OWORD *)((char *)v8 + 12);
  }
  *((_OWORD *)this + 1) = v8[0];
  *(_OWORD *)((char *)this + 28) = v5;
}

```

## disassembly

```asm
0x18000a1bc  push    rbx
0x18000a1be  sub     rsp, 70h
0x18000a1c2  mov     rax, cs:__security_cookie
0x18000a1c9  xor     rax, rsp
0x18000a1cc  mov     [rsp+78h+var_18], rax
0x18000a1d1  xorps   xmm0, xmm0
0x18000a1d4  mov     rax, r8
0x18000a1d7  mov     rbx, rcx
0x18000a1da  movups  xmmword ptr [rsp+78h+var_38], xmm0
0x18000a1df  movups  xmmword ptr [rsp+78h+var_38+0Ch], xmm0
0x18000a1e4  test    r8, r8
0x18000a1e7  jz      short loc_18000A1EF
0x18000a1e9  mov     [rcx+8], rax
0x18000a1ed  jmp     short loc_18000A1F3
0x18000a1ef  mov     rax, [rbx+8]
0x18000a1f3  test    rdx, rdx
0x18000a1f6  jz      short loc_18000A1FC
0x18000a1f8  mov     [rbx+30h], rdx
0x18000a1fc  mov     r9d, 1Ch; unsigned int
0x18000a202  lea     r8, [rsp+78h+var_38]; void *
0x18000a207  mov     rcx, rax; this
0x18000a20a  lea     edx, [r9+24h]; unsigned int
0x18000a20e  call    ?ReadExtendedHeader@CLogFile@@QEAAXKPEAXK@Z; CLogFile::ReadExtendedHeader(ulong,void *,ulong)
0x18000a213  mov     rcx, [rbx+8]
0x18000a217  add     rcx, 50h ; 'P'; this
0x18000a21b  call    ?IsShutdown@CLogFileHeader@@QEBAHXZ; CLogFileHeader::IsShutdown(void)
0x18000a220  test    eax, eax
0x18000a222  jz      short loc_18000A235
0x18000a224  mov     eax, dword ptr [rsp+78h+var_38+4]
0x18000a228  cmp     dword ptr [rsp+78h+var_38], eax
0x18000a22c  jz      short loc_18000A235
0x18000a22e  movups  xmm1, xmmword ptr [rsp+78h+var_38+0Ch]
0x18000a233  jmp     short loc_18000A256
0x18000a235  or      dword ptr [rbx], 1
0x18000a238  lea     rdx, [rsp+78h+var_58]
0x18000a23d  mov     rcx, rbx
0x18000a240  call    ?QueryLogInfo@CLog@@AEAA?AU_LogInfo@@XZ; CLog::QueryLogInfo(void)
0x18000a245  movups  xmm0, xmmword ptr [rax]
0x18000a248  movups  xmm1, xmmword ptr [rax+0Ch]
0x18000a24c  movups  xmmword ptr [rsp+78h+var_38], xmm0
0x18000a251  movups  xmmword ptr [rsp+78h+var_38+0Ch], xmm1
0x18000a256  movups  xmm0, xmmword ptr [rsp+78h+var_38]
0x18000a25b  movups  xmmword ptr [rbx+10h], xmm0
0x18000a25f  movups  xmmword ptr [rbx+1Ch], xmm1
0x18000a263  mov     rcx, [rsp+78h+var_18]
0x18000a268  xor     rcx, rsp; StackCookie
0x18000a26b  call    __security_check_cookie
0x18000a270  add     rsp, 70h
0x18000a274  pop     rbx
0x18000a275  retn
```
