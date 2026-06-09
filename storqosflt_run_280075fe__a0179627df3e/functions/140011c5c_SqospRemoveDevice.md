# SqospRemoveDevice

- ea: `0x140011c5c`
- end: `0x140011dbe`
- name: `SqospRemoveDevice`
- size: `354`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400111bc`
- `0x140012990`

## callees

- `0x140003940`
- `0x140004a8c`
- `0x1400078a8`
- `0x140011c5c`

## import_xrefs

- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140011c9d`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140011c9d`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x140011cf6`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x140011cf6`
- `FLTMGR!FltReleasePushLockEx` at `0x140011ce1`
- `FLTMGR!FltReleasePushLockEx` at `0x140011d75`
- `FLTMGR!FltReleasePushLockEx` at `0x140011ce1`
- `FLTMGR!FltReleasePushLockEx` at `0x140011d75`

## pseudocode

```c
__int64 __fastcall SqospRemoveDevice(__int64 a1)
{
  __int64 *v2; // rbx
  _QWORD *v3; // rsi
  _QWORD *v4; // r14
  __int64 *v5; // rcx
  __int64 **v6; // rax
  _QWORD **v7; // rax
  _QWORD *v8; // rbx
  _QWORD *v9; // rcx
  _QWORD *v10; // rax
  __int64 result; // rax
  KSPIN_LOCK *v12; // rcx

  SqospTeardownVolumeStatsReporting((PFLT_CONTEXT)a1);
  v2 = (__int64 *)(a1 + 160);
  v3 = (_QWORD *)(a1 + 168);
  if ( *(_QWORD *)(a1 + 160) )
  {
    v4 = (_QWORD *)(a1 + 160);
  }
  else
  {
    if ( !*v3 )
      goto LABEL_8;
    v4 = (_QWORD *)(a1 + 160);
  }
  FltAcquirePushLockExclusiveEx(&SqosGlobals, 0);
  v5 = (__int64 *)*v2;
  if ( *(__int64 **)(*v2 + 8) != v2 || (v6 = *(__int64 ***)(a1 + 168), *v6 != v2) )
    __fastfail(3u);
  *v6 = v5;
  v5[1] = (__int64)v6;
  *v3 = 0;
  *v4 = 0;
  FltReleasePushLockEx(&SqosGlobals, 0);
LABEL_8:
  FltAcquirePushLockSharedEx(&SqosGlobals, 0);
  v7 = (_QWORD **)qword_14000D160;
  if ( (qword_14000D160 & 1) == 0 )
    goto LABEL_11;
  if ( qword_14000D160 != 1 )
  {
    v8 = (_QWORD *)(qword_14000D160 ^ ((unsigned __int64)&qword_14000D158 + 1));
    while ( v8 )
    {
      SqospRemoveFlow(v8 - 8);
      v7 = (_QWORD **)v8[1];
      if ( v7 )
      {
        v9 = *v7;
        if ( *v7 )
        {
          do
          {
            v8 = v9;
            v9 = (_QWORD *)*v9;
          }
          while ( v9 );
        }
        else
        {
LABEL_11:
          v8 = v7;
        }
      }
      else
      {
        do
        {
          v10 = v8;
          v8 = (_QWORD *)(v8[2] & 0xFFFFFFFFFFFFFFFCuLL);
        }
        while ( v8 && (_QWORD *)*v8 != v10 );
      }
    }
  }
  result = FltReleasePushLockEx(&SqosGlobals, 0);
  v12 = *(KSPIN_LOCK **)(a1 + 176);
  if ( v12 )
  {
    SqospRemoveFlow(v12);
    result = SqospReleaseClient(*(PVOID *)(a1 + 176));
    *(_QWORD *)(a1 + 176) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140011c5c  push    rbx
0x140011c5e  push    rsi
0x140011c5f  push    rdi
0x140011c60  push    r14
0x140011c62  sub     rsp, 28h
0x140011c66  mov     rdi, rcx
0x140011c69  call    SqospTeardownVolumeStatsReporting
0x140011c6e  lea     rbx, [rdi+0A0h]
0x140011c75  cmp     qword ptr [rbx], 0
0x140011c79  lea     rsi, [rdi+0A8h]
0x140011c80  jnz     short loc_140011C91
0x140011c82  cmp     qword ptr [rsi], 0
0x140011c86  jz      short loc_140011CED
0x140011c88  lea     r14, [rdi+0A0h]
0x140011c8f  jmp     short loc_140011C94
0x140011c91  mov     r14, rbx
0x140011c94  xor     edx, edx
0x140011c96  lea     rcx, SqosGlobals
0x140011c9d  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140011ca4  nop     dword ptr [rax+rax+00h]
0x140011ca9  mov     rcx, [rbx]
0x140011cac  cmp     [rcx+8], rbx
0x140011cb0  jnz     loc_140011DB7
0x140011cb6  mov     rax, [rbx+8]
0x140011cba  cmp     [rax], rbx
0x140011cbd  jnz     loc_140011DB7
0x140011cc3  mov     [rax], rcx
0x140011cc6  xor     edx, edx
0x140011cc8  mov     [rcx+8], rax
0x140011ccc  lea     rcx, SqosGlobals
0x140011cd3  mov     qword ptr [rsi], 0
0x140011cda  mov     qword ptr [r14], 0
0x140011ce1  call    cs:__imp_FltReleasePushLockEx
0x140011ce8  nop     dword ptr [rax+rax+00h]
0x140011ced  xor     edx, edx
0x140011cef  lea     rcx, SqosGlobals
0x140011cf6  call    cs:__imp_FltAcquirePushLockSharedEx
0x140011cfd  nop     dword ptr [rax+rax+00h]
0x140011d02  mov     rax, cs:qword_14000D160
0x140011d09  test    al, 1
0x140011d0b  jz      short loc_140011D23
0x140011d0d  cmp     rax, 1
0x140011d11  jz      short loc_140011D6C
0x140011d13  lea     rbx, qword_14000D158
0x140011d1a  or      rbx, 1
0x140011d1e  xor     rbx, rax
0x140011d21  jmp     short loc_140011D67
0x140011d23  mov     rbx, rax
0x140011d26  jmp     short loc_140011D67
0x140011d28  lea     rcx, [rbx-40h]; SpinLock
0x140011d2c  mov     rdx, rdi
0x140011d2f  call    SqospRemoveFlow
0x140011d34  mov     rax, [rbx+8]
0x140011d38  test    rax, rax
0x140011d3b  jz      short loc_140011D5A
0x140011d3d  mov     rcx, [rax]
0x140011d40  test    rcx, rcx
0x140011d43  jz      short loc_140011D23
0x140011d45  mov     rax, [rcx]
0x140011d48  mov     rbx, rcx
0x140011d4b  mov     rcx, rax
0x140011d4e  test    rax, rax
0x140011d51  jnz     short loc_140011D45
0x140011d53  jmp     short loc_140011D67
0x140011d55  cmp     [rbx], rax
0x140011d58  jz      short loc_140011D67
0x140011d5a  mov     rax, rbx
0x140011d5d  mov     rbx, [rbx+10h]
0x140011d61  and     rbx, 0FFFFFFFFFFFFFFFCh
0x140011d65  jnz     short loc_140011D55
0x140011d67  test    rbx, rbx
0x140011d6a  jnz     short loc_140011D28
0x140011d6c  xor     edx, edx
0x140011d6e  lea     rcx, SqosGlobals
0x140011d75  call    cs:__imp_FltReleasePushLockEx
0x140011d7c  nop     dword ptr [rax+rax+00h]
0x140011d81  mov     rcx, [rdi+0B0h]; SpinLock
0x140011d88  test    rcx, rcx
0x140011d8b  jz      short loc_140011DAC
0x140011d8d  mov     rdx, rdi
0x140011d90  call    SqospRemoveFlow
0x140011d95  mov     rcx, [rdi+0B0h]; Entry
0x140011d9c  call    SqospReleaseClient
0x140011da1  mov     qword ptr [rdi+0B0h], 0
0x140011dac  add     rsp, 28h
0x140011db0  pop     r14
0x140011db2  pop     rdi
0x140011db3  pop     rsi
0x140011db4  pop     rbx
0x140011db5  retn
0x140011db7  mov     ecx, 3
0x140011dbc  int     29h; Win8: RtlFailFast(ecx)
```
