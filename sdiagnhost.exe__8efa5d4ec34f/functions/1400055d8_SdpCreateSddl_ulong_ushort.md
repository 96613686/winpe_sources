# SdpCreateSddl(ulong,ushort * *)

- ea: `0x1400055d8`
- end: `0x1400057b0`
- name: `?SdpCreateSddl@@YAJKPEAPEAG@Z`
- size: `472`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1400057b8`

## callees

- `0x140001ed8`
- `0x1400055d8`
- `0x140005964`
- `0x140005a50`
- `0x140005d7c`
- `0x140005eb8`
- `0x140006050`
- `0x1400068c0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x140005780`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14000578f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14000579d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140005780`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14000578f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14000579d`

## string_xrefs

- `0x140005623`: `SdpCreateSddl`
- `0x140005693`: `SdpCreateSddl`
- `0x1400056bc`: `SdpCreateSddl`
- `0x1400056ee`: `SdpCreateSddl`
- `0x14000572a`: `SdpCreateSddl`
- `0x140005757`: `SdpCreateSddl`

## pseudocode

```c
__int64 __fastcall SdpCreateSddl(unsigned int a1, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // rsi
  unsigned int v4; // ebx
  int v5; // r8d
  int v6; // r9d
  int IsAdmin; // eax
  int IsSystem; // eax
  int v9; // eax
  unsigned int v10; // ecx
  int UserSid; // eax
  unsigned int v12; // ecx
  unsigned __int16 *v13; // rax
  unsigned int v14; // ecx
  unsigned __int16 *v15; // rdi
  int v16; // eax
  unsigned int v17; // ecx
  int v18; // eax
  unsigned int v19; // ecx
  unsigned __int16 *v21; // [rsp+20h] [rbp-10h] BYREF
  int v22; // [rsp+60h] [rbp+30h] BYREF
  int v23; // [rsp+68h] [rbp+38h] BYREF
  unsigned __int16 *v24; // [rsp+70h] [rbp+40h] BYREF
  unsigned __int16 *v25; // [rsp+78h] [rbp+48h] BYREF

  v2 = 0;
  v22 = 0;
  v23 = 0;
  v25 = 0;
  v21 = 0;
  v24 = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 2363;
    v6 = -2147024809;
LABEL_3:
    SdpDebugTrace(a1, L"SdpCreateSddl", v5, v6);
    return v4;
  }
  IsAdmin = SdpIsAdmin(&v22);
  v4 = IsAdmin;
  if ( IsAdmin < 0 )
  {
    v6 = IsAdmin;
    v5 = 2383;
    goto LABEL_3;
  }
  IsSystem = SdpIsSystem(&v23);
  v4 = IsSystem;
  if ( IsSystem < 0 )
  {
    v6 = IsSystem;
    v5 = 2386;
    goto LABEL_3;
  }
  if ( v22 || v23 )
  {
    v18 = SdpStrCpy(&v25, L"O:BAG:BAD:P(A;OICI;0x3;;;SY)(A;OICI;0x3;;;BA)");
    v4 = v18;
    if ( v18 < 0 )
    {
      SdpDebugTrace(v19, L"SdpCreateSddl", 2390, v18);
      v15 = v25;
      goto LABEL_22;
    }
    v15 = v25;
LABEL_21:
    *a2 = v15;
    v15 = 0;
LABEL_22:
    if ( v15 )
      operator delete[](v15);
    goto LABEL_24;
  }
  v9 = SdpStrCpy(&v21, L"O:BAG:BAD:P(A;OICI;0x3;;;SY)(A;OICI;0x3;;;BA)(A;OICI;0x3;;;%s)");
  v4 = v9;
  if ( v9 >= 0 )
  {
    UserSid = SdpGetUserSid(&v24);
    v4 = UserSid;
    if ( UserSid < 0 )
    {
      SdpDebugTrace(v12, L"SdpCreateSddl", 2397, UserSid);
      v2 = v24;
      goto LABEL_24;
    }
    v13 = (unsigned __int16 *)operator new[](0x800u);
    v15 = v13;
    if ( !v13 )
    {
      v4 = -2147024882;
      SdpDebugTrace(v14, L"SdpCreateSddl", 2400, -2147024882);
      v2 = v24;
      goto LABEL_22;
    }
    v2 = v24;
    v16 = StringCchPrintfW(v13, 0x400u, v21, v24);
    v4 = v16;
    if ( v16 < 0 )
    {
      SdpDebugTrace(v17, L"SdpCreateSddl", 2403, v16);
      goto LABEL_22;
    }
    goto LABEL_21;
  }
  SdpDebugTrace(v10, L"SdpCreateSddl", 2394, v9);
LABEL_24:
  if ( v21 )
    operator delete[](v21);
  if ( v2 )
    operator delete[](v2);
  return v4;
}

```

## disassembly

```asm
0x1400055d8  mov     [rsp-28h+arg_0], ecx
0x1400055dc  push    rbp
0x1400055dd  push    rbx
0x1400055de  push    rsi
0x1400055df  push    rdi
0x1400055e0  push    r14
0x1400055e2  mov     rbp, rsp
0x1400055e5  sub     rsp, 30h
0x1400055e9  xor     esi, esi
0x1400055eb  mov     [rbp+arg_0], 0
0x1400055f2  mov     [rbp+arg_8], 0
0x1400055f9  mov     r14, rdx
0x1400055fc  mov     [rbp+arg_18], 0
0x140005604  mov     [rbp+var_10], 0
0x14000560c  mov     [rbp+arg_10], rsi
0x140005610  test    rdx, rdx
0x140005613  jnz     short loc_140005634
0x140005615  mov     ebx, 80070057h
0x14000561a  mov     r8d, 93Bh; int
0x140005620  mov     r9d, ebx; int
0x140005623  lea     rdx, aSdpcreatesddl; "SdpCreateSddl"
0x14000562a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x14000562f  jmp     loc_1400057A3
0x140005634  lea     rcx, [rbp+arg_0]; int *
0x140005638  call    ?SdpIsAdmin@@YAJPEAH@Z; SdpIsAdmin(int *)
0x14000563d  mov     ebx, eax
0x14000563f  test    eax, eax
0x140005641  jns     short loc_14000564E
0x140005643  mov     r9d, eax
0x140005646  mov     r8d, 94Fh
0x14000564c  jmp     short loc_140005623
0x14000564e  lea     rcx, [rbp+arg_8]; int *
0x140005652  call    ?SdpIsSystem@@YAJPEAH@Z; SdpIsSystem(int *)
0x140005657  mov     ebx, eax
0x140005659  test    eax, eax
0x14000565b  jns     short loc_140005668
0x14000565d  mov     r9d, eax
0x140005660  mov     r8d, 952h
0x140005666  jmp     short loc_140005623
0x140005668  cmp     [rbp+arg_0], esi
0x14000566b  jnz     loc_14000573E
0x140005671  cmp     [rbp+arg_8], esi
0x140005674  jnz     loc_14000573E
0x14000567a  lea     rdx, aOBagBadPAOici0_0; "O:BAG:BAD:P(A;OICI;0x3;;;SY)(A;OICI;0x3"...
0x140005681  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x140005685  call    ?SdpStrCpy@@YAJPEAPEAGPEBG@Z; SdpStrCpy(ushort * *,ushort const *)
0x14000568a  mov     ebx, eax
0x14000568c  test    eax, eax
0x14000568e  jns     short loc_1400056AA
0x140005690  mov     r9d, eax; int
0x140005693  lea     rdx, aSdpcreatesddl; "SdpCreateSddl"
0x14000569a  mov     r8d, 95Ah; int
0x1400056a0  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1400056a5  jmp     loc_140005786
0x1400056aa  lea     rcx, [rbp+arg_10]; unsigned __int16 **
0x1400056ae  call    ?SdpGetUserSid@@YAJPEAPEAG@Z; SdpGetUserSid(ushort * *)
0x1400056b3  mov     ebx, eax
0x1400056b5  test    eax, eax
0x1400056b7  jns     short loc_1400056D7
0x1400056b9  mov     r9d, eax; int
0x1400056bc  lea     rdx, aSdpcreatesddl; "SdpCreateSddl"
0x1400056c3  mov     r8d, 95Dh; int
0x1400056c9  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1400056ce  mov     rsi, [rbp+arg_10]
0x1400056d2  jmp     loc_140005786
0x1400056d7  mov     ecx, 800h; unsigned __int64
0x1400056dc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400056e1  mov     rdi, rax
0x1400056e4  test    rax, rax
0x1400056e7  jnz     short loc_140005709
0x1400056e9  mov     ebx, 8007000Eh
0x1400056ee  lea     rdx, aSdpcreatesddl; "SdpCreateSddl"
0x1400056f5  mov     r9d, ebx; int
0x1400056f8  mov     r8d, 960h; int
0x1400056fe  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x140005703  mov     rsi, [rbp+arg_10]
0x140005707  jmp     short loc_140005778
0x140005709  mov     rsi, [rbp+arg_10]
0x14000570d  mov     edx, 400h; unsigned __int64
0x140005712  mov     r8, [rbp+var_10]; unsigned __int16 *
0x140005716  mov     r9, rsi
0x140005719  mov     rcx, rax; unsigned __int16 *
0x14000571c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140005721  mov     ebx, eax
0x140005723  test    eax, eax
0x140005725  jns     short loc_140005773
0x140005727  mov     r9d, eax; int
0x14000572a  lea     rdx, aSdpcreatesddl; "SdpCreateSddl"
0x140005731  mov     r8d, 963h; int
0x140005737  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x14000573c  jmp     short loc_140005778
0x14000573e  lea     rdx, aOBagBadPAOici0; "O:BAG:BAD:P(A;OICI;0x3;;;SY)(A;OICI;0x3"...
0x140005745  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x140005749  call    ?SdpStrCpy@@YAJPEAPEAGPEBG@Z; SdpStrCpy(ushort * *,ushort const *)
0x14000574e  mov     ebx, eax
0x140005750  test    eax, eax
0x140005752  jns     short loc_14000576F
0x140005754  mov     r9d, eax; int
0x140005757  lea     rdx, aSdpcreatesddl; "SdpCreateSddl"
0x14000575e  mov     r8d, 956h; int
0x140005764  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x140005769  mov     rdi, [rbp+arg_18]
0x14000576d  jmp     short loc_140005778
0x14000576f  mov     rdi, [rbp+arg_18]
0x140005773  mov     [r14], rdi
0x140005776  xor     edi, edi
0x140005778  test    rdi, rdi
0x14000577b  jz      short loc_140005786
0x14000577d  mov     rcx, rdi
0x140005780  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140005786  mov     rcx, [rbp+var_10]
0x14000578a  test    rcx, rcx
0x14000578d  jz      short loc_140005795
0x14000578f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140005795  test    rsi, rsi
0x140005798  jz      short loc_1400057A3
0x14000579a  mov     rcx, rsi
0x14000579d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1400057a3  mov     eax, ebx
0x1400057a5  add     rsp, 30h
0x1400057a9  pop     r14
0x1400057ab  pop     rdi
0x1400057ac  pop     rsi
0x1400057ad  pop     rbx
0x1400057ae  pop     rbp
0x1400057af  retn
```
