# SdpCreateSddl(ulong,ushort * *)

- ea: `0x180026bf4`
- end: `0x180026de5`
- name: `?SdpCreateSddl@@YAJKPEAPEAG@Z`
- size: `497`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180026dec`

## callees

- `0x1800012a4`
- `0x1800012b0`
- `0x180002978`
- `0x180026bf4`
- `0x180026fa0`
- `0x1800271ec`
- `0x18002744c`
- `0x18002778c`
- `0x180027aa0`

## string_xrefs

- `0x180026c3f`: `SdpCreateSddl`
- `0x180026cb4`: `SdpCreateSddl`
- `0x180026ce2`: `SdpCreateSddl`
- `0x180026d19`: `SdpCreateSddl`
- `0x180026d58`: `SdpCreateSddl`
- `0x180026d8a`: `SdpCreateSddl`

## pseudocode

```c
__int64 __fastcall SdpCreateSddl(__int64 a1, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // rsi
  unsigned int v4; // ebx
  int v5; // r8d
  int v6; // r9d
  int IsAdmin; // eax
  int IsSystem; // eax
  int v9; // eax
  int UserSid; // eax
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rdi
  int v13; // eax
  int v14; // eax
  void *Block; // [rsp+20h] [rbp-10h] BYREF
  int v17; // [rsp+60h] [rbp+30h] BYREF
  int v18; // [rsp+68h] [rbp+38h] BYREF
  unsigned __int16 *v19; // [rsp+70h] [rbp+40h] BYREF
  unsigned __int16 *v20; // [rsp+78h] [rbp+48h] BYREF

  v2 = 0;
  v17 = 0;
  v18 = 0;
  v20 = 0;
  Block = 0;
  v19 = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 2363;
    v6 = -2147024809;
LABEL_3:
    SdpDebugTrace(1u, L"SdpCreateSddl", v5, v6);
    return v4;
  }
  IsAdmin = SdpIsAdmin(&v17);
  v4 = IsAdmin;
  if ( IsAdmin < 0 )
  {
    v6 = IsAdmin;
    v5 = 2383;
    goto LABEL_3;
  }
  IsSystem = SdpIsSystem(&v18);
  v4 = IsSystem;
  if ( IsSystem < 0 )
  {
    v6 = IsSystem;
    v5 = 2386;
    goto LABEL_3;
  }
  if ( v17 || v18 )
  {
    v14 = SdpStrCpy(&v20, L"D:P(A;OICI;GA;;;SY)(A;OICI;GA;;;BA)");
    v4 = v14;
    if ( v14 < 0 )
    {
      SdpDebugTrace(1u, L"SdpCreateSddl", 2390, v14);
      v12 = v20;
      goto LABEL_22;
    }
    v12 = v20;
LABEL_21:
    *a2 = v12;
    v12 = 0;
LABEL_22:
    if ( v12 )
      operator delete(v12);
    goto LABEL_24;
  }
  v9 = SdpStrCpy((unsigned __int16 **)&Block, L"D:P(A;OICI;GA;;;SY)(A;OICI;GA;;;BA)(A;OICI;GA;;;%s)");
  v4 = v9;
  if ( v9 >= 0 )
  {
    UserSid = SdpGetUserSid(&v19);
    v4 = UserSid;
    if ( UserSid < 0 )
    {
      SdpDebugTrace(1u, L"SdpCreateSddl", 2397, UserSid);
      v2 = v19;
      goto LABEL_24;
    }
    v11 = (unsigned __int16 *)operator new[](0x800u);
    v12 = v11;
    if ( !v11 )
    {
      v4 = -2147024882;
      SdpDebugTrace(1u, L"SdpCreateSddl", 2400, -2147024882);
      v2 = v19;
      goto LABEL_22;
    }
    v2 = v19;
    v13 = StringCchPrintfW(v11, 0x400u, (const unsigned __int16 *)Block, v19);
    v4 = v13;
    if ( v13 < 0 )
    {
      SdpDebugTrace(1u, L"SdpCreateSddl", 2403, v13);
      goto LABEL_22;
    }
    goto LABEL_21;
  }
  SdpDebugTrace(1u, L"SdpCreateSddl", 2394, v9);
LABEL_24:
  if ( Block )
    operator delete(Block);
  if ( v2 )
    operator delete(v2);
  return v4;
}

```

## disassembly

```asm
0x180026bf4  mov     [rsp-28h+arg_0], ecx
0x180026bf8  push    rbp
0x180026bf9  push    rbx
0x180026bfa  push    rsi
0x180026bfb  push    rdi
0x180026bfc  push    r14
0x180026bfe  mov     rbp, rsp
0x180026c01  sub     rsp, 30h
0x180026c05  xor     esi, esi
0x180026c07  mov     [rbp+arg_0], 0
0x180026c0e  mov     [rbp+arg_8], 0
0x180026c15  mov     r14, rdx
0x180026c18  mov     [rbp+arg_18], 0
0x180026c20  mov     [rbp+Block], 0
0x180026c28  mov     [rbp+arg_10], rsi
0x180026c2c  test    rdx, rdx
0x180026c2f  jnz     short loc_180026C55
0x180026c31  mov     ebx, 80070057h
0x180026c36  mov     r8d, 93Bh; int
0x180026c3c  mov     r9d, ebx; int
0x180026c3f  lea     rdx, aSdpcreatesddl; "SdpCreateSddl"
0x180026c46  mov     ecx, 1; Level
0x180026c4b  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180026c50  jmp     loc_180026DD8
0x180026c55  lea     rcx, [rbp+arg_0]; int *
0x180026c59  call    ?SdpIsAdmin@@YAJPEAH@Z; SdpIsAdmin(int *)
0x180026c5e  mov     ebx, eax
0x180026c60  test    eax, eax
0x180026c62  jns     short loc_180026C6F
0x180026c64  mov     r9d, eax
0x180026c67  mov     r8d, 94Fh
0x180026c6d  jmp     short loc_180026C3F
0x180026c6f  lea     rcx, [rbp+arg_8]; int *
0x180026c73  call    ?SdpIsSystem@@YAJPEAH@Z; SdpIsSystem(int *)
0x180026c78  mov     ebx, eax
0x180026c7a  test    eax, eax
0x180026c7c  jns     short loc_180026C89
0x180026c7e  mov     r9d, eax
0x180026c81  mov     r8d, 952h
0x180026c87  jmp     short loc_180026C3F
0x180026c89  cmp     [rbp+arg_0], esi
0x180026c8c  jnz     loc_180026D71
0x180026c92  cmp     [rbp+arg_8], esi
0x180026c95  jnz     loc_180026D71
0x180026c9b  lea     rdx, aDPAOiciGaSyAOi_0; "D:P(A;OICI;GA;;;SY)(A;OICI;GA;;;BA)(A;O"...
0x180026ca2  lea     rcx, [rbp+Block]; unsigned __int16 **
0x180026ca6  call    ?SdpStrCpy@@YAJPEAPEAGPEBG@Z; SdpStrCpy(ushort * *,ushort const *)
0x180026cab  mov     ebx, eax
0x180026cad  test    eax, eax
0x180026caf  jns     short loc_180026CD0
0x180026cb1  mov     r9d, eax; int
0x180026cb4  lea     rdx, aSdpcreatesddl; "SdpCreateSddl"
0x180026cbb  mov     r8d, 95Ah; int
0x180026cc1  mov     ecx, 1; Level
0x180026cc6  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180026ccb  jmp     loc_180026DBD
0x180026cd0  lea     rcx, [rbp+arg_10]; unsigned __int16 **
0x180026cd4  call    ?SdpGetUserSid@@YAJPEAPEAG@Z; SdpGetUserSid(ushort * *)
0x180026cd9  mov     ebx, eax
0x180026cdb  test    eax, eax
0x180026cdd  jns     short loc_180026D02
0x180026cdf  mov     r9d, eax; int
0x180026ce2  lea     rdx, aSdpcreatesddl; "SdpCreateSddl"
0x180026ce9  mov     r8d, 95Dh; int
0x180026cef  mov     ecx, 1; Level
0x180026cf4  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180026cf9  mov     rsi, [rbp+arg_10]
0x180026cfd  jmp     loc_180026DBD
0x180026d02  mov     ecx, 800h; unsigned __int64
0x180026d07  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180026d0c  mov     rdi, rax
0x180026d0f  test    rax, rax
0x180026d12  jnz     short loc_180026D37
0x180026d14  mov     ebx, 8007000Eh
0x180026d19  lea     rdx, aSdpcreatesddl; "SdpCreateSddl"
0x180026d20  mov     r9d, ebx; int
0x180026d23  lea     ecx, [rax+1]; Level
0x180026d26  mov     r8d, 960h; int
0x180026d2c  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180026d31  mov     rsi, [rbp+arg_10]
0x180026d35  jmp     short loc_180026DB0
0x180026d37  mov     rsi, [rbp+arg_10]
0x180026d3b  mov     edx, 400h; unsigned __int64
0x180026d40  mov     r8, [rbp+Block]; unsigned __int16 *
0x180026d44  mov     r9, rsi
0x180026d47  mov     rcx, rax; unsigned __int16 *
0x180026d4a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026d4f  mov     ebx, eax
0x180026d51  test    eax, eax
0x180026d53  jns     short loc_180026DAB
0x180026d55  mov     r9d, eax; int
0x180026d58  lea     rdx, aSdpcreatesddl; "SdpCreateSddl"
0x180026d5f  mov     r8d, 963h; int
0x180026d65  mov     ecx, 1; Level
0x180026d6a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180026d6f  jmp     short loc_180026DB0
0x180026d71  lea     rdx, aDPAOiciGaSyAOi; "D:P(A;OICI;GA;;;SY)(A;OICI;GA;;;BA)"
0x180026d78  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x180026d7c  call    ?SdpStrCpy@@YAJPEAPEAGPEBG@Z; SdpStrCpy(ushort * *,ushort const *)
0x180026d81  mov     ebx, eax
0x180026d83  test    eax, eax
0x180026d85  jns     short loc_180026DA7
0x180026d87  mov     r9d, eax; int
0x180026d8a  lea     rdx, aSdpcreatesddl; "SdpCreateSddl"
0x180026d91  mov     r8d, 956h; int
0x180026d97  mov     ecx, 1; Level
0x180026d9c  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180026da1  mov     rdi, [rbp+arg_18]
0x180026da5  jmp     short loc_180026DB0
0x180026da7  mov     rdi, [rbp+arg_18]
0x180026dab  mov     [r14], rdi
0x180026dae  xor     edi, edi
0x180026db0  test    rdi, rdi
0x180026db3  jz      short loc_180026DBD
0x180026db5  mov     rcx, rdi; Block
0x180026db8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026dbd  mov     rcx, [rbp+Block]; Block
0x180026dc1  test    rcx, rcx
0x180026dc4  jz      short loc_180026DCB
0x180026dc6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026dcb  test    rsi, rsi
0x180026dce  jz      short loc_180026DD8
0x180026dd0  mov     rcx, rsi; Block
0x180026dd3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026dd8  mov     eax, ebx
0x180026dda  add     rsp, 30h
0x180026dde  pop     r14
0x180026de0  pop     rdi
0x180026de1  pop     rsi
0x180026de2  pop     rbx
0x180026de3  pop     rbp
0x180026de4  retn
```
