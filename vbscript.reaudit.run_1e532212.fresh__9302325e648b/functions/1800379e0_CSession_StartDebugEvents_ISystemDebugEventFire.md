# CSession::StartDebugEvents(ISystemDebugEventFire *)

- ea: `0x1800379e0`
- end: `0x180037b79`
- name: `?StartDebugEvents@CSession@@QEAAJPEAUISystemDebugEventFire@@@Z`
- size: `409`
- prototype: `__int64 __fastcall(CSession *__hidden this, struct ISystemDebugEventFire *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800403a0`

## callees

- `0x1800379e0`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180037ad3`
- `KERNEL32!GetTickCount` at `0x180037ad3`
- `KERNEL32!GetCurrentProcessId` at `0x180037a43`
- `KERNEL32!GetCurrentProcessId` at `0x180037a43`
- `KERNEL32!GetCurrentThreadId` at `0x180037a8e`
- `KERNEL32!GetCurrentThreadId` at `0x180037a8e`

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
0x1800379e0  push    rbp
0x1800379e2  push    rbx
0x1800379e3  push    rsi
0x1800379e4  push    rdi
0x1800379e5  lea     rbp, [rsp-3Fh]
0x1800379ea  sub     rsp, 88h
0x1800379f1  mov     rax, cs:__security_cookie
0x1800379f8  xor     rax, rsp
0x1800379fb  mov     [rbp+57h+var_30], rax
0x1800379ff  mov     rbx, rcx
0x180037a02  test    rdx, rdx
0x180037a05  jz      loc_180037B6E
0x180037a0b  mov     [rcx+78h], rdx
0x180037a0f  mov     rcx, rdx
0x180037a12  mov     rax, [rdx]
0x180037a15  mov     rax, [rax+8]
0x180037a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037a1e  movups  xmm0, xmmword ptr cs:aVbscript_0; "VBScript"
0x180037a25  xor     eax, eax
0x180037a27  mov     [rbp+57h+var_70], ax
0x180037a2b  movdqu  [rbp+57h+var_80], xmm0
0x180037a30  xorps   xmm0, xmm0
0x180037a33  movups  [rbp+57h+var_4E], xmm0
0x180037a37  movups  [rbp+57h+var_4E+0Eh], xmm0
0x180037a3b  movups  [rbp+57h+var_6E], xmm0
0x180037a3f  movups  [rbp+57h+var_5E], xmm0
0x180037a43  call    cs:__imp_GetCurrentProcessId
0x180037a49  mov     esi, 3Ah ; ':'
0x180037a4e  mov     r8d, eax
0x180037a51  mov     [rbp+57h+var_70], si
0x180037a55  lea     edi, [rsi-33h]
0x180037a58  mov     r9d, edi
0x180037a5b  mov     eax, 0CCCCCCCDh
0x180037a60  mul     r8d
0x180037a63  shr     edx, 3
0x180037a66  movzx   eax, dx
0x180037a69  shl     ax, 2
0x180037a6d  lea     ecx, [rax+rdx]
0x180037a70  add     cx, cx
0x180037a73  sub     r8w, cx
0x180037a77  add     r8w, 30h ; '0'
0x180037a7c  mov     word ptr [rbp+r9*2+57h+var_6E], r8w
0x180037a82  dec     r9
0x180037a85  mov     r8d, edx
0x180037a88  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x180037a8c  jnz     short loc_180037A5B
0x180037a8e  call    cs:__imp_GetCurrentThreadId
0x180037a94  mov     word ptr [rbp+57h+var_5E], si
0x180037a98  mov     r10, rdi
0x180037a9b  mov     r9d, eax
0x180037a9e  mov     eax, 0CCCCCCCDh
0x180037aa3  mul     r9d
0x180037aa6  shr     edx, 3
0x180037aa9  movzx   ecx, dx
0x180037aac  shl     cx, 2
0x180037ab0  lea     r8d, [rcx+rdx]
0x180037ab4  add     r8w, r8w
0x180037ab8  sub     r9w, r8w
0x180037abc  add     r9w, 30h ; '0'
0x180037ac1  mov     word ptr [rbp+r10*2+57h+var_5E+2], r9w
0x180037ac7  dec     r10
0x180037aca  mov     r9d, edx
0x180037acd  cmp     r10, 0FFFFFFFFFFFFFFFFh
0x180037ad1  jnz     short loc_180037A9E
0x180037ad3  call    cs:__imp_GetTickCount
0x180037ad9  mov     r9d, eax
0x180037adc  mov     word ptr [rbp+57h+var_4E+2], si
0x180037ae0  mov     eax, 0CCCCCCCDh
0x180037ae5  mul     r9d
0x180037ae8  shr     edx, 3
0x180037aeb  movzx   ecx, dx
0x180037aee  shl     cx, 2
0x180037af2  lea     r8d, [rcx+rdx]
0x180037af6  add     r8w, r8w
0x180037afa  sub     r9w, r8w
0x180037afe  add     r9w, 30h ; '0'
0x180037b03  mov     word ptr [rbp+rdi*2+57h+var_4E+4], r9w
0x180037b09  dec     rdi
0x180037b0c  mov     r9d, edx
0x180037b0f  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180037b13  jnz     short loc_180037AE0
0x180037b15  mov     rcx, [rbx+78h]
0x180037b19  lea     r8, [rbp+57h+var_80]
0x180037b1d  xor     eax, eax
0x180037b1f  lea     rdx, DEBUG_EVENT_GUID
0x180037b26  mov     [rbp+57h+var_3A], ax
0x180037b2a  mov     rax, [rcx]
0x180037b2d  mov     rax, [rax+18h]
0x180037b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037b36  mov     edi, eax
0x180037b38  test    eax, eax
0x180037b3a  jns     short loc_180037B75
0x180037b3c  mov     rcx, [rbx+78h]
0x180037b40  mov     rdx, [rcx]
0x180037b43  mov     rax, [rdx+10h]
0x180037b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037b4c  mov     eax, edi
0x180037b4e  mov     qword ptr [rbx+78h], 0
0x180037b56  mov     rcx, [rbp+57h+var_30]
0x180037b5a  xor     rcx, rsp; StackCookie
0x180037b5d  call    __security_check_cookie
0x180037b62  add     rsp, 88h
0x180037b69  pop     rdi
0x180037b6a  pop     rsi
0x180037b6b  pop     rbx
0x180037b6c  pop     rbp
0x180037b6d  retn
0x180037b6e  mov     eax, 80004005h
0x180037b73  jmp     short loc_180037B56
0x180037b75  xor     eax, eax
0x180037b77  jmp     short loc_180037B56
```
