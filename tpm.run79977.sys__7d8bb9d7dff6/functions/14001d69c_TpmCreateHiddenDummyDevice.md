# TpmCreateHiddenDummyDevice

- ea: `0x14001d69c`
- end: `0x14001d7fb`
- name: `TpmCreateHiddenDummyDevice`
- size: `351`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140013da0`

## callees

- `0x14001a88c`
- `0x14001d69c`
- `0x140039740`
- `0x140039780`

## pseudocode

```c
__int64 __fastcall TpmCreateHiddenDummyDevice(__int64 a1)
{
  int v1; // ebx
  char IsAllowRemovalRequested; // al
  int v3; // edx
  __int64 v5; // [rsp+30h] [rbp-49h] BYREF
  __int64 v6; // [rsp+38h] [rbp-41h] BYREF
  _QWORD v7[4]; // [rsp+40h] [rbp-39h] BYREF
  int v8; // [rsp+60h] [rbp-19h]
  int v9; // [rsp+64h] [rbp-15h]
  __int128 v10; // [rsp+68h] [rbp-11h] BYREF
  __int64 v11; // [rsp+78h] [rbp-1h]
  __int64 v12; // [rsp+80h] [rbp+7h]
  __int128 v13; // [rsp+88h] [rbp+Fh]
  __int64 v14; // [rsp+98h] [rbp+1Fh]
  _OWORD v15[2]; // [rsp+A0h] [rbp+27h] BYREF

  v6 = a1;
  v14 = 0;
  v5 = 0;
  v11 = 0;
  v7[0] = 40;
  v7[1] = TpmEvtDeviceFileCreateFail;
  memset(v15, 0, 28);
  v12 = 0x400000001LL;
  v10 = 0;
  LODWORD(v10) = 56;
  v13 = 0;
  v7[2] = 0;
  v7[3] = 0;
  v8 = 2;
  v9 = 1;
  (*((void (__fastcall **)(PKDPC, __int64, _QWORD *, __int128 *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 71))(
    WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
    a1,
    v7,
    &v10);
  v1 = (*((__int64 (__fastcall **)(PKDPC, __int64 *, _QWORD, __int64 *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 75))(
         WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
         &v6,
         0,
         &v5);
  if ( v1 >= 0 )
  {
    *(__m128i *)((char *)v15 + 4) = _mm_load_si128((const __m128i *)&_xmm);
    LODWORD(v15[0]) = 28;
    *(_QWORD *)((char *)&v15[1] + 4) = 0x200000002LL;
    IsAllowRemovalRequested = TpmIsAllowRemovalRequested();
    v3 = v15[1];
    DWORD2(v15[0]) = 1;
    if ( IsAllowRemovalRequested )
      v3 = 0;
    LODWORD(v15[1]) = v3;
    (*((void (__fastcall **)(PKDPC, __int64, _OWORD *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 29))(
      WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
      v5,
      v15);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x14001d69c  mov     [rsp-8+arg_8], rbx
0x14001d6a1  push    rbp
0x14001d6a2  lea     rbp, [rsp-57h]
0x14001d6a7  sub     rsp, 0D0h
0x14001d6ae  mov     rax, cs:__security_cookie
0x14001d6b5  xor     rax, rsp
0x14001d6b8  mov     [rbp+57h+var_10], rax
0x14001d6bc  xor     eax, eax
0x14001d6be  mov     [rbp+57h+var_98], rcx
0x14001d6c2  mov     [rbp+57h+var_38], rax
0x14001d6c6  lea     r9, [rbp+57h+var_68]
0x14001d6ca  xorps   xmm1, xmm1
0x14001d6cd  mov     [rbp+57h+var_A0], 0
0x14001d6d5  movups  [rbp+57h+var_58], xmm1
0x14001d6d9  mov     [rbp+57h+var_90], 28h ; '('
0x14001d6e1  lea     rax, TpmEvtDeviceFileCreateFail
0x14001d6e8  mov     [rbp+57h+var_88], rax
0x14001d6ec  xorps   xmm0, xmm0
0x14001d6ef  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14001d6f6  lea     r8, [rbp+57h+var_90]
0x14001d6fa  movups  [rbp+57h+var_30], xmm0
0x14001d6fe  mov     dword ptr [rbp+57h+var_58+8], 1
0x14001d705  mov     rdx, rcx
0x14001d708  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14001d70f  movups  [rbp+57h+var_68], xmm1
0x14001d713  mov     dword ptr [rbp+57h+var_68], 38h ; '8'
0x14001d71a  movups  [rbp+57h+var_30+0Ch], xmm0
0x14001d71e  mov     dword ptr [rbp+57h+var_58+0Ch], 4
0x14001d725  movups  [rbp+57h+var_48], xmm1
0x14001d729  mov     [rbp+57h+var_80], 0
0x14001d731  mov     [rbp+57h+var_78], 0
0x14001d739  mov     [rbp+57h+var_70], 2
0x14001d740  mov     [rbp+57h+var_6C], 1
0x14001d747  mov     rax, [rax+238h]
0x14001d74e  call    _guard_dispatch_icall
0x14001d753  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14001d75a  lea     r9, [rbp+57h+var_A0]
0x14001d75e  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14001d765  lea     rdx, [rbp+57h+var_98]
0x14001d769  xor     r8d, r8d
0x14001d76c  mov     rax, [rax+258h]
0x14001d773  call    _guard_dispatch_icall
0x14001d778  mov     ebx, eax
0x14001d77a  test    eax, eax
0x14001d77c  js      short loc_14001D7DB
0x14001d77e  movdqa  xmm0, cs:__xmm@00000002000000020000000200000002
0x14001d786  movdqu  [rbp+57h+var_30+4], xmm0
0x14001d78b  mov     dword ptr [rbp+57h+var_30], 1Ch
0x14001d792  mov     [rbp+57h+var_1C], 2
0x14001d799  mov     [rbp+57h+var_18], 2
0x14001d7a0  call    TpmIsAllowRemovalRequested
0x14001d7a5  mov     edx, [rbp+57h+var_20]
0x14001d7a8  lea     r8, [rbp+57h+var_30]
0x14001d7ac  xor     ecx, ecx
0x14001d7ae  mov     dword ptr [rbp+57h+var_30+8], 1
0x14001d7b5  test    al, al
0x14001d7b7  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14001d7be  cmovnz  edx, ecx
0x14001d7c1  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14001d7c8  mov     [rbp+57h+var_20], edx
0x14001d7cb  mov     rax, [rax+0E8h]
0x14001d7d2  mov     rdx, [rbp+57h+var_A0]
0x14001d7d6  call    _guard_dispatch_icall
0x14001d7db  mov     eax, ebx
0x14001d7dd  mov     rcx, [rbp+57h+var_10]
0x14001d7e1  xor     rcx, rsp; StackCookie
0x14001d7e4  call    __security_check_cookie
0x14001d7e9  mov     rbx, [rsp+0D0h+arg_8]
0x14001d7f1  add     rsp, 0D0h
0x14001d7f8  pop     rbp
0x14001d7f9  retn
```
