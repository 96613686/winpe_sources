# p9fs::util::GetAttributesByHandle(_LX_UTIL_FS_CONTEXT const &,void *,void *,p9fs::util::GetAttributeFlags)

- ea: `0x18002c040`
- end: `0x18002c128`
- name: `?GetAttributesByHandle@util@p9fs@@YA?AV?$BasicExpected@U_FILE_STAT_LX_INFORMATION@@J@1@AEBU_LX_UTIL_FS_CONTEXT@@PEAX1W4GetAttributeFlags@12@@Z`
- size: `232`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18002bc50`
- `0x18002bf20`

## callees

- `0x180004120`
- `0x180004c80`
- `0x18002c040`

## import_xrefs

- `lxutil!LxUtilFsReadLinkLength` at `0x18002c0d2`
- `lxutil!LxUtilFsReadLinkLength` at `0x18002c0d2`
- `lxutil!LxUtilFsQueryStatLxInformation` at `0x18002c086`
- `lxutil!LxUtilFsQueryStatLxInformation` at `0x18002c086`

## pseudocode

```c
__int64 __fastcall p9fs::util::GetAttributesByHandle(__int64 a1, __int64 a2, __int64 a3, __int64 a4, char a5)
{
  int StatLxInformation; // eax
  int v10; // ecx
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  _OWORD v17[3]; // [rsp+20h] [rbp-41h] BYREF
  _OWORD v18[3]; // [rsp+50h] [rbp-11h] BYREF

  memset_0(v17, 0, 0x60u);
  StatLxInformation = LxUtilFsQueryStatLxInformation(a3, a2, v17);
  if ( StatLxInformation >= 0 )
  {
    if ( (a5 & 1) == 0 && (WORD4(v18[0]) & 0x400) != 0 && (unsigned int)(HIDWORD(v18[0]) + 1610612733) <= 0x1A )
    {
      v10 = 67109377;
      if ( _bittest(&v10, HIDWORD(v18[0]) + 1610612733) )
      {
        if ( !*(_QWORD *)&v18[0] )
          LxUtilFsReadLinkLength(a2, a3, a4, v18);
      }
    }
    v11 = v17[1];
    *(_OWORD *)(a1 + 8) = v17[0];
    *(_BYTE *)a1 = 1;
    v12 = v17[2];
    *(_OWORD *)(a1 + 24) = v11;
    v13 = v18[0];
    *(_OWORD *)(a1 + 40) = v12;
    v14 = v18[1];
    *(_OWORD *)(a1 + 56) = v13;
    v15 = v18[2];
    *(_OWORD *)(a1 + 72) = v14;
    *(_OWORD *)(a1 + 88) = v15;
  }
  else
  {
    *(_BYTE *)a1 = 0;
    *(_DWORD *)(a1 + 8) = StatLxInformation;
  }
  return a1;
}

```

## disassembly

```asm
0x18002c040  push    rbp
0x18002c042  push    rbx
0x18002c043  push    rsi
0x18002c044  push    rdi
0x18002c045  push    r14
0x18002c047  lea     rbp, [rsp-2Fh]
0x18002c04c  sub     rsp, 90h
0x18002c053  mov     rax, cs:__security_cookie
0x18002c05a  xor     rax, rsp
0x18002c05d  mov     [rbp+4Fh+var_30], rax
0x18002c061  mov     rdi, rdx
0x18002c064  mov     rsi, r8
0x18002c067  xor     edx, edx; Val
0x18002c069  mov     rbx, rcx
0x18002c06c  lea     rcx, [rbp+4Fh+var_90]; void *
0x18002c070  mov     r14, r9
0x18002c073  lea     r8d, [rdx+60h]; Size
0x18002c077  call    memset_0
0x18002c07c  lea     r8, [rbp+4Fh+var_90]
0x18002c080  mov     rdx, rdi
0x18002c083  mov     rcx, rsi
0x18002c086  call    cs:__imp_LxUtilFsQueryStatLxInformation
0x18002c08c  test    eax, eax
0x18002c08e  jns     short loc_18002C098
0x18002c090  mov     byte ptr [rbx], 0
0x18002c093  mov     [rbx+8], eax
0x18002c096  jmp     short loc_18002C10B
0x18002c098  test    [rbp+4Fh+arg_20], 1
0x18002c09c  jnz     short loc_18002C0D8
0x18002c09e  test    dword ptr [rbp+4Fh+var_60+8], 400h
0x18002c0a5  jz      short loc_18002C0D8
0x18002c0a7  mov     eax, dword ptr [rbp+4Fh+var_60+0Ch]
0x18002c0aa  add     eax, 5FFFFFFDh
0x18002c0af  cmp     eax, 1Ah
0x18002c0b2  ja      short loc_18002C0D8
0x18002c0b4  mov     ecx, 4000201h
0x18002c0b9  bt      ecx, eax
0x18002c0bc  jnb     short loc_18002C0D8
0x18002c0be  cmp     qword ptr [rbp+4Fh+var_60], 0
0x18002c0c3  jnz     short loc_18002C0D8
0x18002c0c5  lea     r9, [rbp+4Fh+var_60]
0x18002c0c9  mov     r8, r14
0x18002c0cc  mov     rdx, rsi
0x18002c0cf  mov     rcx, rdi
0x18002c0d2  call    cs:__imp_LxUtilFsReadLinkLength
0x18002c0d8  movaps  xmm0, [rbp+4Fh+var_90]
0x18002c0dc  movaps  xmm1, [rbp+4Fh+var_80]
0x18002c0e0  movups  xmmword ptr [rbx+8], xmm0
0x18002c0e4  mov     byte ptr [rbx], 1
0x18002c0e7  movaps  xmm0, [rbp+4Fh+var_70]
0x18002c0eb  movups  xmmword ptr [rbx+18h], xmm1
0x18002c0ef  movaps  xmm1, [rbp+4Fh+var_60]
0x18002c0f3  movups  xmmword ptr [rbx+28h], xmm0
0x18002c0f7  movaps  xmm0, [rbp+4Fh+var_50]
0x18002c0fb  movups  xmmword ptr [rbx+38h], xmm1
0x18002c0ff  movaps  xmm1, [rbp+4Fh+var_40]
0x18002c103  movups  xmmword ptr [rbx+48h], xmm0
0x18002c107  movups  xmmword ptr [rbx+58h], xmm1
0x18002c10b  mov     rax, rbx
0x18002c10e  mov     rcx, [rbp+4Fh+var_30]
0x18002c112  xor     rcx, rsp; StackCookie
0x18002c115  call    __security_check_cookie
0x18002c11a  add     rsp, 90h
0x18002c121  pop     r14
0x18002c123  pop     rdi
0x18002c124  pop     rsi
0x18002c125  pop     rbx
0x18002c126  pop     rbp
0x18002c127  retn
```
