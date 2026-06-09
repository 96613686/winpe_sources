# SumTraceIPAddress

- ea: `0x140013f74`
- end: `0x140014050`
- name: `SumTraceIPAddress`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400413a0`

## callees

- `0x140013f74`
- `0x14002a3e0`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140014031`
- `ntoskrnl!EtwWrite` at `0x140014031`

## pseudocode

```c
void __fastcall SumTraceIPAddress(__int64 a1, ULONGLONG a2, __int16 *a3, const wchar_t *a4)
{
  __int64 v4; // rax
  int v5; // eax
  __int16 v6; // ax
  _WORD *v7; // rax
  const EVENT_DESCRIPTOR *v8; // rdx
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-40h] BYREF
  _WORD *v10; // [rsp+40h] [rbp-30h]
  __int64 v11; // [rsp+48h] [rbp-28h]
  const wchar_t *v12; // [rsp+50h] [rbp-20h]
  int v13; // [rsp+58h] [rbp-18h]
  int v14; // [rsp+5Ch] [rbp-14h]

  if ( a3 )
  {
    UserData.Ptr = a2;
    *(_QWORD *)&UserData.Size = 16;
    if ( a4 )
    {
      v4 = -1;
      do
        ++v4;
      while ( a4[v4] );
      v5 = 2 * v4 + 2;
    }
    else
    {
      v5 = 10;
    }
    v13 = v5;
    v6 = *a3;
    if ( !a4 )
      a4 = L"NULL";
    v14 = 0;
    v12 = a4;
    if ( v6 == 2 )
    {
      v7 = a3 + 2;
      v11 = 4;
      v8 = (const EVENT_DESCRIPTOR *)IPV4Event;
    }
    else
    {
      if ( v6 != 23 )
        return;
      v7 = a3 + 4;
      v11 = 16;
      v8 = &IPV6Event;
    }
    v10 = v7;
    EtwWrite(KSumRegHandle, v8, 0, 3u, &UserData);
  }
}

```

## disassembly

```asm
0x140013f74  test    r8, r8
0x140013f77  jz      locret_14001404E
0x140013f7d  push    rbp
0x140013f7e  mov     rbp, rsp
0x140013f81  sub     rsp, 70h
0x140013f85  mov     rax, cs:__security_cookie
0x140013f8c  xor     rax, rsp
0x140013f8f  mov     [rbp+var_10], rax
0x140013f93  mov     rcx, cs:KSumRegHandle; RegHandle
0x140013f9a  xor     r10d, r10d
0x140013f9d  mov     [rbp+var_40.Ptr], rdx
0x140013fa1  mov     qword ptr [rbp+var_40.Size], 10h
0x140013fa9  test    r9, r9
0x140013fac  jz      short loc_140013FC5
0x140013fae  or      rax, 0FFFFFFFFFFFFFFFFh
0x140013fb2  inc     rax
0x140013fb5  cmp     [r9+rax*2], r10w
0x140013fba  jnz     short loc_140013FB2
0x140013fbc  lea     eax, ds:2[rax*2]
0x140013fc3  jmp     short loc_140013FCA
0x140013fc5  mov     eax, 0Ah
0x140013fca  test    r9, r9
0x140013fcd  mov     [rbp+var_18], eax
0x140013fd0  movzx   eax, word ptr [r8]
0x140013fd4  lea     rdx, aNull_0; "NULL"
0x140013fdb  cmovz   r9, rdx
0x140013fdf  mov     [rbp+var_14], r10d
0x140013fe3  mov     [rbp+var_20], r9
0x140013fe7  cmp     ax, 2
0x140013feb  jnz     short loc_140014002
0x140013fed  lea     rax, [r8+4]
0x140013ff1  mov     [rbp+var_28], 4
0x140013ff9  lea     rdx, IPV4Event
0x140014000  jmp     short loc_14001401B
0x140014002  cmp     ax, 17h
0x140014006  jnz     short loc_14001403D
0x140014008  lea     rax, [r8+8]
0x14001400c  mov     [rbp+var_28], 10h
0x140014014  lea     rdx, IPV6Event; EventDescriptor
0x14001401b  mov     [rbp+var_30], rax
0x14001401f  mov     r9d, 3; UserDataCount
0x140014025  lea     rax, [rbp+var_40]
0x140014029  xor     r8d, r8d; ActivityId
0x14001402c  mov     [rsp+70h+UserData], rax; UserData
0x140014031  call    cs:__imp_EtwWrite
0x140014038  nop     dword ptr [rax+rax+00h]
0x14001403d  mov     rcx, [rbp+var_10]
0x140014041  xor     rcx, rsp; StackCookie
0x140014044  call    __security_check_cookie
0x140014049  add     rsp, 70h
0x14001404d  pop     rbp
0x14001404e  retn
```
