# CSession::StartDebugEvents(ISystemDebugEventFire *)

- ea: `0x180039814`
- end: `0x1800399c0`
- name: `?StartDebugEvents@CSession@@QEAAJPEAUISystemDebugEventFire@@@Z`
- size: `428`
- prototype: `__int64 __fastcall(CSession *__hidden this, struct ISystemDebugEventFire *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180041a70`

## callees

- `0x180039814`
- `0x180079490`
- `0x18007a010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180039913`
- `KERNEL32!GetTickCount` at `0x180039913`
- `KERNEL32!GetCurrentProcessId` at `0x180039877`
- `KERNEL32!GetCurrentProcessId` at `0x180039877`
- `KERNEL32!GetCurrentThreadId` at `0x1800398c8`
- `KERNEL32!GetCurrentThreadId` at `0x1800398c8`

## pseudocode

```c
__int64 __fastcall CSession::StartDebugEvents(CSession *this, struct ISystemDebugEventFire *a2)
{
  DWORD CurrentProcessId; // r8d
  __int64 v4; // rdi
  __int64 i; // r9
  DWORD CurrentThreadId; // eax
  __int64 v7; // r10
  DWORD v8; // r9d
  __int64 v9; // r9
  __int64 v10; // rcx
  int v11; // edi
  __int64 result; // rax
  __int128 v13; // [rsp+20h] [rbp-29h] BYREF
  __int16 v14; // [rsp+30h] [rbp-19h]
  _BYTE v15[62]; // [rsp+32h] [rbp-17h] BYREF

  if ( !a2 )
    return 2147500037LL;
  *((_QWORD *)this + 15) = a2;
  (*(void (__fastcall **)(struct ISystemDebugEventFire *))(*(_QWORD *)a2 + 8LL))(a2);
  v13 = *(_OWORD *)L"VBScript";
  memset(v15, 0, sizeof(v15));
  CurrentProcessId = GetCurrentProcessId();
  v14 = 58;
  v4 = 7;
  for ( i = 7; i != -1; --i )
  {
    *(_WORD *)&v15[2 * i] = CurrentProcessId % 0xA + 48;
    CurrentProcessId /= 0xAu;
  }
  CurrentThreadId = GetCurrentThreadId();
  strcpy(&v15[16], ":");
  v7 = 7;
  v8 = CurrentThreadId;
  do
  {
    *(_WORD *)&v15[2 * v7-- + 18] = v8 % 0xA + 48;
    v8 /= 0xAu;
  }
  while ( v7 != -1 );
  LODWORD(v9) = GetTickCount();
  strcpy(&v15[34], ":");
  do
  {
    *(_WORD *)&v15[2 * v4-- + 36] = (unsigned int)v9 % 0xA + 48;
    v9 = (unsigned int)v9 / 0xA;
  }
  while ( v4 != -1 );
  v10 = *((_QWORD *)this + 15);
  *(_WORD *)&v15[52] = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int128 *, __int64))(*(_QWORD *)v10 + 24LL))(
          v10,
          DEBUG_EVENT_GUID,
          &v13,
          v9);
  if ( v11 >= 0 )
    return 0;
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 15) + 16LL))(*((_QWORD *)this + 15));
  result = (unsigned int)v11;
  *((_QWORD *)this + 15) = 0;
  return result;
}

```

## disassembly

```asm
0x180039814  push    rbp
0x180039816  push    rbx
0x180039817  push    rsi
0x180039818  push    rdi
0x180039819  lea     rbp, [rsp-3Fh]
0x18003981e  sub     rsp, 88h
0x180039825  mov     rax, cs:__security_cookie
0x18003982c  xor     rax, rsp
0x18003982f  mov     [rbp+57h+var_30], rax
0x180039833  mov     rbx, rcx
0x180039836  test    rdx, rdx
0x180039839  jz      loc_1800399B5
0x18003983f  mov     [rcx+78h], rdx
0x180039843  mov     rcx, rdx
0x180039846  mov     rax, [rdx]
0x180039849  mov     rax, [rax+8]
0x18003984d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039852  movups  xmm0, xmmword ptr cs:aVbscript_0; "VBScript"
0x180039859  xor     eax, eax
0x18003985b  mov     [rbp+57h+var_70], ax
0x18003985f  movdqu  [rbp+57h+var_80], xmm0
0x180039864  xorps   xmm0, xmm0
0x180039867  movups  [rbp+57h+var_4E], xmm0
0x18003986b  movups  [rbp+57h+var_4E+0Eh], xmm0
0x18003986f  movups  [rbp+57h+var_6E], xmm0
0x180039873  movups  [rbp+57h+var_5E], xmm0
0x180039877  call    cs:__imp_GetCurrentProcessId
0x18003987e  nop     dword ptr [rax+rax+00h]
0x180039883  mov     esi, 3Ah ; ':'
0x180039888  mov     r8d, eax
0x18003988b  mov     [rbp+57h+var_70], si
0x18003988f  lea     edi, [rsi-33h]
0x180039892  mov     r9d, edi
0x180039895  mov     eax, 0CCCCCCCDh
0x18003989a  mul     r8d
0x18003989d  shr     edx, 3
0x1800398a0  movzx   eax, dx
0x1800398a3  shl     ax, 2
0x1800398a7  lea     ecx, [rax+rdx]
0x1800398aa  add     cx, cx
0x1800398ad  sub     r8w, cx
0x1800398b1  add     r8w, 30h ; '0'
0x1800398b6  mov     word ptr [rbp+r9*2+57h+var_6E], r8w
0x1800398bc  dec     r9
0x1800398bf  mov     r8d, edx
0x1800398c2  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x1800398c6  jnz     short loc_180039895
0x1800398c8  call    cs:__imp_GetCurrentThreadId
0x1800398cf  nop     dword ptr [rax+rax+00h]
0x1800398d4  mov     word ptr [rbp+57h+var_5E], si
0x1800398d8  mov     r10, rdi
0x1800398db  mov     r9d, eax
0x1800398de  mov     eax, 0CCCCCCCDh
0x1800398e3  mul     r9d
0x1800398e6  shr     edx, 3
0x1800398e9  movzx   ecx, dx
0x1800398ec  shl     cx, 2
0x1800398f0  lea     r8d, [rcx+rdx]
0x1800398f4  add     r8w, r8w
0x1800398f8  sub     r9w, r8w
0x1800398fc  add     r9w, 30h ; '0'
0x180039901  mov     word ptr [rbp+r10*2+57h+var_5E+2], r9w
0x180039907  dec     r10
0x18003990a  mov     r9d, edx
0x18003990d  cmp     r10, 0FFFFFFFFFFFFFFFFh
0x180039911  jnz     short loc_1800398DE
0x180039913  call    cs:__imp_GetTickCount
0x18003991a  nop     dword ptr [rax+rax+00h]
0x18003991f  mov     r9d, eax
0x180039922  mov     word ptr [rbp+57h+var_4E+2], si
0x180039926  mov     eax, 0CCCCCCCDh
0x18003992b  mul     r9d
0x18003992e  shr     edx, 3
0x180039931  movzx   ecx, dx
0x180039934  shl     cx, 2
0x180039938  lea     r8d, [rcx+rdx]
0x18003993c  add     r8w, r8w
0x180039940  sub     r9w, r8w
0x180039944  add     r9w, 30h ; '0'
0x180039949  mov     word ptr [rbp+rdi*2+57h+var_4E+4], r9w
0x18003994f  dec     rdi
0x180039952  mov     r9d, edx
0x180039955  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180039959  jnz     short loc_180039926
0x18003995b  mov     rcx, [rbx+78h]
0x18003995f  lea     r8, [rbp+57h+var_80]
0x180039963  xor     eax, eax
0x180039965  lea     rdx, DEBUG_EVENT_GUID
0x18003996c  mov     [rbp+57h+var_3A], ax
0x180039970  mov     rax, [rcx]
0x180039973  mov     rax, [rax+18h]
0x180039977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003997c  mov     edi, eax
0x18003997e  test    eax, eax
0x180039980  jns     short loc_1800399BC
0x180039982  mov     rcx, [rbx+78h]
0x180039986  mov     rdx, [rcx]
0x180039989  mov     rax, [rdx+10h]
0x18003998d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039992  mov     eax, edi
0x180039994  mov     qword ptr [rbx+78h], 0
0x18003999c  mov     rcx, [rbp+57h+var_30]
0x1800399a0  xor     rcx, rsp; StackCookie
0x1800399a3  call    __security_check_cookie
0x1800399a8  add     rsp, 88h
0x1800399af  pop     rdi
0x1800399b0  pop     rsi
0x1800399b1  pop     rbx
0x1800399b2  pop     rbp
0x1800399b3  retn
0x1800399b5  mov     eax, 80004005h
0x1800399ba  jmp     short loc_18003999C
0x1800399bc  xor     eax, eax
0x1800399be  jmp     short loc_18003999C
```
