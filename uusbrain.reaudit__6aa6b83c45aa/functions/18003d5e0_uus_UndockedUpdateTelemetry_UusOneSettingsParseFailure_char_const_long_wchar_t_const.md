# uus::UndockedUpdateTelemetry::UusOneSettingsParseFailure(char const *,long,wchar_t const *)

- ea: `0x18003d5e0`
- end: `0x18003d71a`
- name: `?UusOneSettingsParseFailure@UndockedUpdateTelemetry@uus@@SAXPEBDJPEB_W@Z`
- size: `314`
- prototype: `void __fastcall(const char *, int, const wchar_t *)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180035cb0`
- `0x180035fe0`
- `0x18004af5e`
- `0x18004afd7`
- `0x18004b050`

## callees

- `0x18000109c`
- `0x18000868c`
- `0x18003d5e0`
- `0x1800427d0`

## pseudocode

```c
void __fastcall uus::UndockedUpdateTelemetry::UusOneSettingsParseFailure(const wchar_t *a1, int a2, const wchar_t *a3)
{
  const struct _tlgProvider_t *v6; // r10
  __int64 v7; // rax
  __int64 v8; // rcx
  int v9; // ecx
  int v10; // eax
  int v11; // [rsp+38h] [rbp-29h] BYREF
  __int64 v12; // [rsp+40h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+48h] [rbp-19h] BYREF
  __int64 *v14; // [rsp+68h] [rbp+7h]
  __int64 v15; // [rsp+70h] [rbp+Fh]
  const wchar_t *v16; // [rsp+78h] [rbp+17h]
  int v17; // [rsp+80h] [rbp+1Fh]
  int v18; // [rsp+84h] [rbp+23h]
  int *v19; // [rsp+88h] [rbp+27h]
  __int64 v20; // [rsp+90h] [rbp+2Fh]
  const wchar_t *v21; // [rsp+98h] [rbp+37h]
  int v22; // [rsp+A0h] [rbp+3Fh]
  int v23; // [rsp+A4h] [rbp+43h]

  v6 = uus::UndockedUpdateTelemetry::Provider();
  if ( *(_DWORD *)v6 > 5u
    && (*((_QWORD *)v6 + 2) & 0x200000000000LL) != 0
    && (*((_QWORD *)v6 + 3) & 0x200000000000LL) == *((_QWORD *)v6 + 3) )
  {
    v7 = -1;
    v11 = a2;
    v12 = 0x1000000;
    if ( a3 )
    {
      v8 = -1;
      do
        ++v8;
      while ( a3[v8] );
      v9 = 2 * v8 + 2;
    }
    else
    {
      a3 = &qword_180050DC0;
      v9 = 2;
    }
    v22 = v9;
    v19 = &v11;
    v21 = a3;
    v23 = 0;
    v20 = 4;
    if ( a1 )
    {
      do
        ++v7;
      while ( *((_BYTE *)a1 + v7) );
      v10 = v7 + 1;
    }
    else
    {
      a1 = &Src;
      v10 = 1;
    }
    v17 = v10;
    v18 = 0;
    v14 = &v12;
    v16 = a1;
    v15 = 8;
    tlgWriteTransfer_EventWriteTransfer((__int64)v6, (unsigned __int8 *)&unk_180057388, 0, 0, 6u, &v13);
  }
}

```

## disassembly

```asm
0x18003d5e0  mov     rax, rsp
0x18003d5e3  mov     [rax+8], rbx
0x18003d5e7  mov     [rax+10h], rsi
0x18003d5eb  mov     [rax+18h], rdi
0x18003d5ef  push    rbp
0x18003d5f0  lea     rbp, [rax-5Fh]
0x18003d5f4  sub     rsp, 0B0h
0x18003d5fb  mov     rax, cs:__security_cookie
0x18003d602  xor     rax, rsp
0x18003d605  mov     [rbp+57h+var_10], rax
0x18003d609  mov     rbx, r8
0x18003d60c  mov     esi, edx
0x18003d60e  mov     rdi, rcx
0x18003d611  call    ?Provider@UndockedUpdateTelemetry@uus@@SAPEBU_tlgProvider_t@@XZ; uus::UndockedUpdateTelemetry::Provider(void)
0x18003d616  mov     r10, rax
0x18003d619  cmp     dword ptr [rax], 5
0x18003d61c  jbe     loc_18003D6F5
0x18003d622  mov     rax, 200000000000h
0x18003d62c  test    [r10+10h], rax
0x18003d630  jz      loc_18003D6F5
0x18003d636  mov     rcx, [r10+18h]
0x18003d63a  and     rcx, rax
0x18003d63d  cmp     rcx, [r10+18h]
0x18003d641  jnz     loc_18003D6F5
0x18003d647  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003d64b  mov     [rbp+57h+var_80], esi
0x18003d64e  xor     edx, edx
0x18003d650  mov     [rbp+57h+var_78], 1000000h
0x18003d658  test    rbx, rbx
0x18003d65b  jz      short loc_18003D672
0x18003d65d  mov     rcx, rax
0x18003d660  inc     rcx
0x18003d663  cmp     [rbx+rcx*2], dx
0x18003d667  jnz     short loc_18003D660
0x18003d669  lea     ecx, ds:2[rcx*2]
0x18003d670  jmp     short loc_18003D67E
0x18003d672  lea     rbx, qword_180050DC0
0x18003d679  mov     ecx, 2
0x18003d67e  mov     [rbp+57h+var_18], ecx
0x18003d681  lea     rcx, [rbp+57h+var_80]
0x18003d685  mov     [rbp+57h+var_30], rcx
0x18003d689  mov     [rbp+57h+var_20], rbx
0x18003d68d  mov     [rbp+57h+var_14], edx
0x18003d690  mov     [rbp+57h+var_28], 4
0x18003d698  test    rdi, rdi
0x18003d69b  jz      short loc_18003D6A9
0x18003d69d  inc     rax
0x18003d6a0  cmp     [rdi+rax], dl
0x18003d6a3  jnz     short loc_18003D69D
0x18003d6a5  inc     eax
0x18003d6a7  jmp     short loc_18003D6B5
0x18003d6a9  lea     rdi, Src
0x18003d6b0  mov     eax, 1
0x18003d6b5  mov     [rbp+57h+var_38], eax
0x18003d6b8  xor     r9d, r9d; int
0x18003d6bb  lea     rax, [rbp+57h+var_78]
0x18003d6bf  mov     [rbp+57h+var_34], edx
0x18003d6c2  mov     [rbp+57h+var_50], rax
0x18003d6c6  lea     rdx, unk_180057388; int
0x18003d6cd  lea     rax, [rbp+57h+var_70]
0x18003d6d1  mov     [rbp+57h+var_40], rdi
0x18003d6d5  mov     [rsp+0B0h+var_88], rax; PEVENT_DATA_DESCRIPTOR
0x18003d6da  xor     r8d, r8d; int
0x18003d6dd  mov     rcx, r10; int
0x18003d6e0  mov     [rsp+0B0h+var_90], 6; ULONG
0x18003d6e8  mov     [rbp+57h+var_48], 8
0x18003d6f0  call    _tlgWriteTransfer_EventWriteTransfer
0x18003d6f5  mov     rcx, [rbp+57h+var_10]
0x18003d6f9  xor     rcx, rsp; StackCookie
0x18003d6fc  call    __security_check_cookie
0x18003d701  lea     r11, [rsp+0B0h+var_s0]
0x18003d709  mov     rbx, [r11+10h]
0x18003d70d  mov     rsi, [r11+18h]
0x18003d711  mov     rdi, [r11+20h]
0x18003d715  mov     rsp, r11
0x18003d718  pop     rbp
0x18003d719  retn
```
