# AddUserToGroup(_UNICODE_STRING *,void *,void *,ulong)

- ea: `0x18000f168`
- end: `0x18000f409`
- name: `?AddUserToGroup@@YAJPEAU_UNICODE_STRING@@PEAX1K@Z`
- size: `673`
- prototype: `int(struct _UNICODE_STRING *, void *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180012acc`

## callees

- `0x180003660`
- `0x18000f168`
- `0x1800132b4`
- `0x180013340`
- `0x1800133e0`
- `0x180013534`

## import_xrefs

- `SAMLIB!SamRidToSid` at `0x18000f258`
- `SAMLIB!SamRidToSid` at `0x18000f258`
- `SAMLIB!SamLookupNamesInDomain2` at `0x18000f222`
- `SAMLIB!SamLookupNamesInDomain2` at `0x18000f222`
- `SAMLIB!SamCloseHandle` at `0x18000f2ff`
- `SAMLIB!SamCloseHandle` at `0x18000f3d8`
- `SAMLIB!SamCloseHandle` at `0x18000f3e2`
- `SAMLIB!SamCloseHandle` at `0x18000f3eb`
- `SAMLIB!SamCloseHandle` at `0x18000f3f5`
- `SAMLIB!SamCloseHandle` at `0x18000f2ff`
- `SAMLIB!SamCloseHandle` at `0x18000f3d8`
- `SAMLIB!SamCloseHandle` at `0x18000f3e2`
- `SAMLIB!SamCloseHandle` at `0x18000f3eb`
- `SAMLIB!SamCloseHandle` at `0x18000f3f5`
- `SAMLIB!SamAddMemberToAlias` at `0x18000f293`
- `SAMLIB!SamAddMemberToAlias` at `0x18000f293`
- `SAMLIB!SamOpenAlias` at `0x18000f281`
- `SAMLIB!SamOpenAlias` at `0x18000f281`
- `SAMLIB!SamFreeMemory` at `0x18000f349`
- `SAMLIB!SamFreeMemory` at `0x18000f38e`
- `SAMLIB!SamFreeMemory` at `0x18000f398`
- `SAMLIB!SamFreeMemory` at `0x18000f349`
- `SAMLIB!SamFreeMemory` at `0x18000f38e`
- `SAMLIB!SamFreeMemory` at `0x18000f398`

## pseudocode

```c
__int64 __fastcall AddUserToGroup(struct _UNICODE_STRING *a1, void *a2, void *a3)
{
  int v5; // ebx
  int v6; // eax
  void *v7; // rsi
  int v8; // eax
  int v9; // r8d
  int v10; // eax
  int v11; // r8d
  int v12; // eax
  int v13; // eax
  unsigned int *v15; // [rsp+40h] [rbp-9h] BYREF
  __int64 v16; // [rsp+48h] [rbp-1h] BYREF
  __int64 v17; // [rsp+50h] [rbp+7h] BYREF
  void *v18; // [rsp+58h] [rbp+Fh] BYREF
  void *v19; // [rsp+60h] [rbp+17h] BYREF
  void *v20; // [rsp+68h] [rbp+1Fh] BYREF
  void *v21; // [rsp+70h] [rbp+27h] BYREF

  v20 = 0;
  v19 = 0;
  v21 = 0;
  v18 = 0;
  v5 = SamHandleForDomain(a2, 0x20031u, 0x20385u, &v21, &v18);
  if ( v5 >= 0 )
  {
    v6 = SamHandleForDomain(a3, 0x2003Fu, 0x20785u, &v20, &v19);
    v7 = v18;
    v5 = v6;
    if ( v6 >= 0 )
    {
      v15 = 0;
      v18 = 0;
      v8 = SamLookupNamesInDomain2(v7, 1, a1, &v15, &v18);
      if ( v8 < 0 )
      {
        v5 = v8 | 0x10000000;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_ZD(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, v9, (_DWORD)a1, v8);
      }
      else
      {
        if ( *(_DWORD *)v18 == 1 )
        {
          v17 = 0;
          v10 = SamRidToSid(v7, *v15, &v17);
          if ( v10 < 0 )
          {
            v5 = v10 | 0x10000000;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_ZdD(*((_QWORD *)WPP_GLOBAL_Control + 2), *v15, v11, (_DWORD)a1, *v15, v10);
          }
          else
          {
            v16 = 0;
            v12 = SamOpenAlias(v19, 1, 545, &v16);
            if ( v12 < 0 )
            {
              v5 = v12 | 0x10000000;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_dD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  70,
                  WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids,
                  545,
                  v5);
              }
            }
            else
            {
              v13 = SamAddMemberToAlias(v16, v17);
              if ( (int)(v13 + 0x80000000) >= 0 && v13 != -1073741485 )
              {
                v5 = v13 | 0x10000000;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  WPP_SF_ZddD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    69,
                    (unsigned int)WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids,
                    (_DWORD)a1,
                    *v15,
                    33,
                    v13);
                }
              }
              SamCloseHandle(v16);
            }
            SamFreeMemory(v17);
          }
        }
        else
        {
          v5 = -805306230;
        }
        SamFreeMemory(v15);
        SamFreeMemory(v18);
      }
      SamCloseHandle(v19);
      SamCloseHandle(v20);
    }
    SamCloseHandle(v7);
    SamCloseHandle(v21);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000f168  push    rbp
0x18000f16a  push    rbx
0x18000f16b  push    rsi
0x18000f16c  push    rdi
0x18000f16d  lea     rbp, [rsp-3Fh]
0x18000f172  sub     rsp, 88h
0x18000f179  mov     rdi, rcx
0x18000f17c  mov     [rbp+57h+var_38], 0
0x18000f184  mov     rax, rdx
0x18000f187  mov     [rbp+57h+var_40], 0
0x18000f18f  lea     rcx, [rbp+57h+var_48]
0x18000f193  mov     [rbp+57h+var_30], 0
0x18000f19b  mov     [rsp+0A0h+var_80], rcx; void **
0x18000f1a0  lea     r9, [rbp+57h+var_30]; void **
0x18000f1a4  mov     rsi, r8
0x18000f1a7  mov     [rbp+57h+var_48], 0
0x18000f1af  mov     rcx, rax; void *
0x18000f1b2  mov     edx, 20031h; unsigned int
0x18000f1b7  mov     r8d, 20385h; unsigned int
0x18000f1bd  call    ?SamHandleForDomain@@YAJPEAXKKPEAPEAX1@Z; SamHandleForDomain(void *,ulong,ulong,void * *,void * *)
0x18000f1c2  mov     ebx, eax
0x18000f1c4  test    eax, eax
0x18000f1c6  js      loc_18000F3FB
0x18000f1cc  lea     rax, [rbp+57h+var_40]
0x18000f1d0  mov     edx, 2003Fh; unsigned int
0x18000f1d5  lea     r9, [rbp+57h+var_38]; void **
0x18000f1d9  mov     [rsp+0A0h+var_80], rax; void **
0x18000f1de  mov     r8d, 20785h; unsigned int
0x18000f1e4  mov     rcx, rsi; void *
0x18000f1e7  call    ?SamHandleForDomain@@YAJPEAXKKPEAPEAX1@Z; SamHandleForDomain(void *,ulong,ulong,void * *,void * *)
0x18000f1ec  mov     rsi, [rbp+57h+var_48]
0x18000f1f0  mov     ebx, eax
0x18000f1f2  test    eax, eax
0x18000f1f4  js      loc_18000F3E8
0x18000f1fa  lea     rax, [rbp+57h+var_48]
0x18000f1fe  mov     [rbp+57h+var_60], 0
0x18000f206  lea     r9, [rbp+57h+var_60]
0x18000f20a  mov     [rsp+0A0h+var_80], rax
0x18000f20f  mov     r8, rdi
0x18000f212  mov     [rbp+57h+var_48], 0
0x18000f21a  mov     edx, 1
0x18000f21f  mov     rcx, rsi
0x18000f222  call    cs:__imp_SamLookupNamesInDomain2
0x18000f228  test    eax, eax
0x18000f22a  js      loc_18000F3A0
0x18000f230  mov     rax, [rbp+57h+var_48]
0x18000f234  cmp     dword ptr [rax], 1
0x18000f237  jz      short loc_18000F243
0x18000f239  mov     ebx, 0D000008Ah
0x18000f23e  jmp     loc_18000F38A
0x18000f243  mov     rdx, [rbp+57h+var_60]
0x18000f247  lea     r8, [rbp+57h+var_50]
0x18000f24b  mov     [rbp+57h+var_50], 0
0x18000f253  mov     rcx, rsi
0x18000f256  mov     edx, [rdx]
0x18000f258  call    cs:__imp_SamRidToSid
0x18000f25e  test    eax, eax
0x18000f260  js      loc_18000F351
0x18000f266  mov     rcx, [rbp+57h+var_40]
0x18000f26a  lea     r9, [rbp+57h+var_58]
0x18000f26e  mov     edx, 1
0x18000f273  mov     [rbp+57h+var_58], 0
0x18000f27b  mov     r8d, 221h
0x18000f281  call    cs:__imp_SamOpenAlias
0x18000f287  test    eax, eax
0x18000f289  js      short loc_18000F307
0x18000f28b  mov     rdx, [rbp+57h+var_50]
0x18000f28f  mov     rcx, [rbp+57h+var_58]
0x18000f293  call    cs:__imp_SamAddMemberToAlias
0x18000f299  mov     edx, 80000000h
0x18000f29e  lea     ecx, [rax+rdx]
0x18000f2a1  test    edx, ecx
0x18000f2a3  jnz     short loc_18000F2FB
0x18000f2a5  cmp     eax, 0C0000153h
0x18000f2aa  jz      short loc_18000F2FB
0x18000f2ac  mov     ebx, eax
0x18000f2ae  bts     ebx, 1Ch
0x18000f2b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2b9  lea     rax, WPP_GLOBAL_Control
0x18000f2c0  cmp     rcx, rax
0x18000f2c3  jz      short loc_18000F2FB
0x18000f2c5  test    byte ptr [rcx+1Ch], 2
0x18000f2c9  jz      short loc_18000F2FB
0x18000f2cb  mov     rax, [rbp+57h+var_60]
0x18000f2cf  mov     edx, 45h ; 'E'
0x18000f2d4  mov     rcx, [rcx+10h]
0x18000f2d8  mov     r9, rdi
0x18000f2db  mov     [rsp+0A0h+var_70], ebx
0x18000f2df  mov     [rsp+0A0h+var_78], 221h
0x18000f2e7  mov     r8d, [rax]
0x18000f2ea  mov     dword ptr [rsp+0A0h+var_80], r8d
0x18000f2ef  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x18000f2f6  call    WPP_SF_ZddD
0x18000f2fb  mov     rcx, [rbp+57h+var_58]
0x18000f2ff  call    cs:__imp_SamCloseHandle
0x18000f305  jmp     short loc_18000F345
0x18000f307  mov     ebx, eax
0x18000f309  bts     ebx, 1Ch
0x18000f30d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f314  lea     rax, WPP_GLOBAL_Control
0x18000f31b  cmp     rcx, rax
0x18000f31e  jz      short loc_18000F345
0x18000f320  test    byte ptr [rcx+1Ch], 2
0x18000f324  jz      short loc_18000F345
0x18000f326  mov     rcx, [rcx+10h]
0x18000f32a  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x18000f331  mov     edx, 46h ; 'F'
0x18000f336  mov     dword ptr [rsp+0A0h+var_80], ebx
0x18000f33a  mov     r9d, 221h
0x18000f340  call    WPP_SF_dD
0x18000f345  mov     rcx, [rbp+57h+var_50]
0x18000f349  call    cs:__imp_SamFreeMemory
0x18000f34f  jmp     short loc_18000F38A
0x18000f351  mov     ebx, eax
0x18000f353  bts     ebx, 1Ch
0x18000f357  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f35e  lea     rax, WPP_GLOBAL_Control
0x18000f365  cmp     rcx, rax
0x18000f368  jz      short loc_18000F38A
0x18000f36a  test    byte ptr [rcx+1Ch], 2
0x18000f36e  jz      short loc_18000F38A
0x18000f370  mov     rax, [rbp+57h+var_60]
0x18000f374  mov     r9, rdi
0x18000f377  mov     rcx, [rcx+10h]
0x18000f37b  mov     [rsp+0A0h+var_78], ebx
0x18000f37f  mov     edx, [rax]
0x18000f381  mov     dword ptr [rsp+0A0h+var_80], edx
0x18000f385  call    WPP_SF_ZdD
0x18000f38a  mov     rcx, [rbp+57h+var_60]
0x18000f38e  call    cs:__imp_SamFreeMemory
0x18000f394  mov     rcx, [rbp+57h+var_48]
0x18000f398  call    cs:__imp_SamFreeMemory
0x18000f39e  jmp     short loc_18000F3D4
0x18000f3a0  mov     ebx, eax
0x18000f3a2  bts     ebx, 1Ch
0x18000f3a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f3ad  lea     rax, WPP_GLOBAL_Control
0x18000f3b4  cmp     rcx, rax
0x18000f3b7  jz      short loc_18000F3D4
0x18000f3b9  test    byte ptr [rcx+1Ch], 2
0x18000f3bd  jz      short loc_18000F3D4
0x18000f3bf  mov     rcx, [rcx+10h]
0x18000f3c3  mov     edx, 48h ; 'H'
0x18000f3c8  mov     r9, rdi
0x18000f3cb  mov     dword ptr [rsp+0A0h+var_80], ebx
0x18000f3cf  call    WPP_SF_ZD
0x18000f3d4  mov     rcx, [rbp+57h+var_40]
0x18000f3d8  call    cs:__imp_SamCloseHandle
0x18000f3de  mov     rcx, [rbp+57h+var_38]
0x18000f3e2  call    cs:__imp_SamCloseHandle
0x18000f3e8  mov     rcx, rsi
0x18000f3eb  call    cs:__imp_SamCloseHandle
0x18000f3f1  mov     rcx, [rbp+57h+var_30]
0x18000f3f5  call    cs:__imp_SamCloseHandle
0x18000f3fb  mov     eax, ebx
0x18000f3fd  add     rsp, 88h
0x18000f404  pop     rdi
0x18000f405  pop     rsi
0x18000f406  pop     rbx
0x18000f407  pop     rbp
0x18000f408  retn
```
