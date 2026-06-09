# TraceError

- ea: `0x14001f130`
- end: `0x14001f27f`
- name: `TraceError`
- size: `335`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `5`
- tags: ``

## callers

- `0x140007a58`
- `0x140007d40`
- `0x14001f410`
- `0x14001f4e0`
- `0x14001f580`
- `0x14001f5e0`
- `0x14001f6c0`
- `0x14001fab0`
- `0x14001fc10`
- `0x14001fe30`
- `0x14001ffd0`
- `0x140022078`

## callees

- `0x140001148`
- `0x140002604`
- `0x14000f684`
- `0x14000f900`
- `0x14001f130`

## pseudocode

```c
void __fastcall TraceError(const char *a1, int a2)
{
  const struct _UNICODE_STRING *LogSessionId; // rdx
  __int16 *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  int Length; // ecx
  int v9; // [rsp+30h] [rbp-39h] BYREF
  __int64 v10; // [rsp+38h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+40h] [rbp-29h] BYREF
  __int64 *v12; // [rsp+60h] [rbp-9h]
  __int64 v13; // [rsp+68h] [rbp-1h]
  _DWORD *v14; // [rsp+70h] [rbp+7h]
  __int64 v15; // [rsp+78h] [rbp+Fh]
  wchar_t *Buffer; // [rsp+80h] [rbp+17h]
  _DWORD v17[2]; // [rsp+88h] [rbp+1Fh] BYREF
  __int16 *v18; // [rsp+90h] [rbp+27h]
  int v19; // [rsp+98h] [rbp+2Fh]
  int v20; // [rsp+9Ch] [rbp+33h]
  int *v21; // [rsp+A0h] [rbp+37h]
  __int64 v22; // [rsp+A8h] [rbp+3Fh]

  if ( (unsigned int)dword_140019000 > 4
    && (qword_140019010 & 0x800000000000LL) != 0
    && (qword_140019018 & 0x800000000000LL) == qword_140019018 )
  {
    v9 = a2;
    LogSessionId = GetLogSessionId();
    v22 = 4;
    v10 = 0x80000000LL;
    v21 = &v9;
    if ( a1 )
    {
      v5 = (__int16 *)a1;
      v6 = -1;
      do
        ++v6;
      while ( a1[v6] );
      v7 = v6 + 1;
    }
    else
    {
      v5 = word_1400161DA;
      v7 = 1;
    }
    v19 = v7;
    v18 = v5;
    v14 = v17;
    v20 = 0;
    v15 = 2;
    Length = LogSessionId->Length;
    Buffer = LogSessionId->Buffer;
    v12 = &v10;
    v17[0] = Length;
    v17[1] = 0;
    v13 = 8;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140019000, (unsigned __int8 *)&word_1400178E6, 0, 0, 7u, &v11);
  }
  WriteLog(0, "%s (0x%08x)", a1, a2);
}

```

## disassembly

```asm
0x14001f130  mov     [rsp-8+arg_10], rbx
0x14001f135  mov     [rsp-8+arg_18], rdi
0x14001f13a  push    rbp
0x14001f13b  lea     rbp, [rsp-57h]
0x14001f140  sub     rsp, 0C0h
0x14001f147  mov     rax, cs:__security_cookie
0x14001f14e  xor     rax, rsp
0x14001f151  mov     [rbp+57h+var_10], rax
0x14001f155  mov     eax, cs:dword_140019000
0x14001f15b  mov     edi, edx
0x14001f15d  mov     rbx, rcx
0x14001f160  cmp     eax, 4
0x14001f163  jbe     loc_14001F249
0x14001f169  mov     rcx, cs:qword_140019018
0x14001f170  mov     rdx, 800000000000h
0x14001f17a  mov     rax, cs:qword_140019010
0x14001f181  test    rdx, rax
0x14001f184  jz      loc_14001F249
0x14001f18a  mov     rax, rcx
0x14001f18d  and     rax, rdx
0x14001f190  cmp     rax, rcx
0x14001f193  jnz     loc_14001F249
0x14001f199  mov     [rbp+57h+var_90], edi
0x14001f19c  call    ?GetLogSessionId@@YAPEBU_UNICODE_STRING@@XZ; GetLogSessionId(void)
0x14001f1a1  mov     rdx, rax
0x14001f1a4  mov     [rbp+57h+var_18], 4
0x14001f1ac  mov     eax, 80000000h
0x14001f1b1  xor     r8d, r8d
0x14001f1b4  mov     [rbp+57h+var_88], rax
0x14001f1b8  lea     rax, [rbp+57h+var_90]
0x14001f1bc  mov     [rbp+57h+var_20], rax
0x14001f1c0  test    rbx, rbx
0x14001f1c3  jz      short loc_14001F1D9
0x14001f1c5  mov     rcx, rbx
0x14001f1c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001f1cc  inc     rax
0x14001f1cf  cmp     [rbx+rax], r8b
0x14001f1d3  jnz     short loc_14001F1CC
0x14001f1d5  inc     eax
0x14001f1d7  jmp     short loc_14001F1E5
0x14001f1d9  lea     rcx, word_1400161DA
0x14001f1e0  mov     eax, 1
0x14001f1e5  mov     [rbp+57h+var_28], eax
0x14001f1e8  xor     r9d, r9d
0x14001f1eb  mov     [rbp+57h+var_30], rcx
0x14001f1ef  lea     rax, [rbp+57h+var_38]
0x14001f1f3  mov     [rbp+57h+var_50], rax
0x14001f1f7  mov     [rbp+57h+var_24], r8d
0x14001f1fb  mov     [rbp+57h+var_48], 2
0x14001f203  mov     rax, [rdx+8]
0x14001f207  movzx   ecx, word ptr [rdx]
0x14001f20a  lea     rdx, word_1400178E6
0x14001f211  mov     [rbp+57h+var_40], rax
0x14001f215  lea     rax, [rbp+57h+var_88]
0x14001f219  mov     [rbp+57h+var_60], rax
0x14001f21d  lea     rax, [rbp+57h+var_80]
0x14001f221  mov     [rbp+57h+var_38], ecx
0x14001f224  lea     rcx, dword_140019000
0x14001f22b  mov     [rsp+0C0h+var_98], rax
0x14001f230  mov     [rsp+0C0h+var_A0], 7
0x14001f238  mov     [rbp+57h+var_34], r8d
0x14001f23c  mov     [rbp+57h+var_58], 8
0x14001f244  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001f249  mov     r9d, edi
0x14001f24c  lea     rdx, aS0x08x; "%s (0x%08x)"
0x14001f253  mov     r8, rbx
0x14001f256  xor     ecx, ecx
0x14001f258  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14001f25d  mov     rcx, [rbp+57h+var_10]
0x14001f261  xor     rcx, rsp; StackCookie
0x14001f264  call    __security_check_cookie
0x14001f269  lea     r11, [rsp+0C0h+var_s0]
0x14001f271  mov     rbx, [r11+20h]
0x14001f275  mov     rdi, [r11+28h]
0x14001f279  mov     rsp, r11
0x14001f27c  pop     rbp
0x14001f27d  retn
```
