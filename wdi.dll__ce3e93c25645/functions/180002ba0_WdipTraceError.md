# WdipTraceError

- ea: `0x180002ba0`
- end: `0x180002e66`
- name: `WdipTraceError`
- size: `710`
- prototype: `signed int(__int64, __int64, int, const wchar_t *, ...)`
- caller_count: `108`
- callee_count: `3`
- tags: ``

## callers

- `0x180001080`
- `0x1800011d0`
- `0x180001370`
- `0x180001470`
- `0x180001550`
- `0x1800015b0`
- `0x180001630`
- `0x180001830`
- `0x180001980`
- `0x180001cf0`
- `0x180002890`
- `0x180002e70`
- `0x1800031e0`
- `0x180003420`
- `0x180003a30`
- `0x180003cc0`
- `0x180003f40`
- `0x180004100`
- `0x1800041a0`
- `0x1800042c0`
- `0x1800048c0`
- `0x180004d20`
- `0x180004da0`
- `0x180004f50`
- `0x180005000`
- `0x180005340`
- `0x180005430`
- `0x180005710`
- `0x1800057d0`
- `0x180005880`
- `0x1800059d0`
- `0x180005ac0`
- `0x180005bb0`
- `0x180005c60`
- `0x180005cf0`
- `0x180005fa0`
- `0x180006290`
- `0x1800063d0`
- `0x1800067c0`
- `0x1800068f0`
- `0x180006a90`
- `0x180006b90`
- `0x180007020`
- `0x180007160`
- `0x180007280`
- `0x1800072f0`
- `0x180007630`
- `0x1800077e0`
- `0x180007a40`
- `0x180007b00`

## callees

- `0x180002ba0`
- `0x180009474`
- `0x18000f1f0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180002cff`
- `msvcrt!_vsnwprintf` at `0x180002cff`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180002e1f`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180002e1f`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180002c0b`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180002c0b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002db1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002db1`

## pseudocode

```c
signed int WdipTraceError(__int64 a1, __int64 a2, int a3, const wchar_t *a4, ...)
{
  __int64 v6; // r14
  __int64 v7; // rdi
  bool v8; // zf
  __int64 v9; // rsi
  signed int result; // eax
  unsigned int v11; // esi
  unsigned int v12; // r13d
  __int64 v13; // rax
  WCHAR *v14; // rdi
  unsigned __int64 v15; // rbx
  unsigned __int64 v16; // rsi
  int v17; // eax
  unsigned __int64 v18; // rcx
  WCHAR *v19; // rax
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // r8
  const wchar_t *v22; // rdx
  __int64 v23; // rcx
  WCHAR *v24; // rax
  unsigned __int64 i; // rbx
  WCHAR *v26; // rcx
  int v27; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v28; // [rsp+38h] [rbp-C8h]
  _BYTE UserData[24]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v30; // [rsp+58h] [rbp-A8h]
  __int128 v31; // [rsp+68h] [rbp-98h]
  __int64 v32; // [rsp+78h] [rbp-88h]
  WCHAR OutputString[1024]; // [rsp+80h] [rbp-80h] BYREF
  va_list va; // [rsp+900h] [rbp+800h] BYREF

  va_start(va, a4);
  v27 = a3;
  memset(UserData, 0, sizeof(UserData));
  v28 = 0;
  v32 = 0;
  v30 = 0;
  v31 = 0;
  if ( !EventEnabled(g_hETW, &WDI_DPS_EVENT_DEBUG) )
    return 0;
  v6 = -1;
  v7 = -1;
  do
    v8 = *(_WORD *)(a1 + 2 * v7++ + 2) == 0;
  while ( !v8 );
  v9 = -1;
  do
    v8 = *(_WORD *)(a2 + 2 * v9++ + 2) == 0;
  while ( !v8 );
  result = StringCchPrintfW(OutputString, 0x400u, L"WDI: %s (%s):line-%d :- ", a1, a2, v27);
  if ( result >= 0 )
  {
    v11 = 2 * v9 + 2;
    LODWORD(v28) = v11;
    v12 = 2 * v7 + 2;
    v13 = -1;
    do
      ++v13;
    while ( OutputString[v13] );
    v14 = &OutputString[v13];
    v15 = 1024 - v13;
    if ( 1024 != v13 )
    {
      if ( v15 <= 0x7FFFFFFF )
      {
        v16 = v15 - 1;
        v17 = _vsnwprintf(&OutputString[v13], v15 - 1, a4, va);
        if ( v17 < 0 || v17 >= v16 )
          v14[v16] = 0;
        v11 = v28;
        v18 = v15;
        v19 = v14;
        do
        {
          if ( !*v19 )
            break;
          ++v19;
          --v18;
        }
        while ( v18 );
        v20 = v15 - v18;
        if ( v18 )
        {
          v21 = v15 - v18;
          v22 = L"\n";
          v23 = 2147483646;
          v24 = &v14[v20];
          for ( i = v15 - v21; i; --i )
          {
            if ( !v23 )
              break;
            if ( !*v22 )
              break;
            *v24++ = *v22++;
            --v23;
          }
          v26 = v24 - 1;
          if ( i )
            v26 = v24;
          *v26 = 0;
        }
      }
      else
      {
        *v14 = 0;
      }
    }
    do
      v8 = v14[++v6] == 0;
    while ( !v8 );
    OutputDebugStringW(OutputString);
    *((_QWORD *)&v30 + 1) = &v27;
    *(_QWORD *)UserData = a1;
    v32 = (unsigned int)(2 * v6 + 2);
    *(_QWORD *)&UserData[8] = v12;
    *(_QWORD *)&UserData[16] = a2;
    *(_QWORD *)&v30 = v11;
    *(_QWORD *)&v31 = 4;
    *((_QWORD *)&v31 + 1) = v14;
    return EventWrite(g_hETW, &WDI_DPS_EVENT_DEBUG, 4u, (PEVENT_DATA_DESCRIPTOR)UserData);
  }
  return result;
}

```

## disassembly

```asm
0x180002ba0  mov     [rsp-8+Format], r9
0x180002ba5  push    rbp
0x180002ba6  push    rbx
0x180002ba7  push    r12
0x180002ba9  push    r15
0x180002bab  lea     rbp, [rsp-7B8h]
0x180002bb3  sub     rsp, 8B8h
0x180002bba  mov     rax, cs:__security_cookie
0x180002bc1  xor     rax, rsp
0x180002bc4  mov     [rbp+7D0h+var_50], rax
0x180002bcb  xorps   xmm0, xmm0
0x180002bce  mov     [rsp+8D0h+var_8A0], r8d
0x180002bd3  mov     r15, rcx
0x180002bd6  mov     r12, rdx
0x180002bd9  xor     ecx, ecx
0x180002bdb  lea     rdx, WDI_DPS_EVENT_DEBUG; EventDescriptor
0x180002be2  mov     ebx, ecx
0x180002be4  mov     qword ptr [rsp+8D0h+UserData], rcx
0x180002be9  mov     [rsp+8D0h+var_898], rcx
0x180002bee  xor     eax, eax
0x180002bf0  mov     rcx, cs:g_hETW; RegHandle
0x180002bf7  movups  xmmword ptr [rsp+8D0h+UserData+8], xmm0
0x180002bfc  mov     [rsp+8D0h+var_858], rax
0x180002c01  movups  [rsp+8D0h+var_878], xmm0
0x180002c06  movups  [rsp+8D0h+var_868], xmm0
0x180002c0b  call    cs:__imp_EventEnabled
0x180002c11  test    al, al
0x180002c13  jz      loc_180002E62
0x180002c19  mov     [rsp+8D0h+var_20], rsi
0x180002c21  mov     [rsp+8D0h+var_28], rdi
0x180002c29  mov     [rsp+8D0h+var_38], r14
0x180002c31  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180002c38  mov     rdi, r14
0x180002c3b  nop     dword ptr [rax+rax+00h]
0x180002c40  cmp     [r15+rdi*2+2], bx
0x180002c46  lea     rdi, [rdi+1]
0x180002c4a  jnz     short loc_180002C40
0x180002c4c  mov     rsi, r14
0x180002c4f  nop
0x180002c50  cmp     [r12+rsi*2+2], bx
0x180002c56  lea     rsi, [rsi+1]
0x180002c5a  jnz     short loc_180002C50
0x180002c5c  mov     eax, [rsp+8D0h+var_8A0]
0x180002c60  lea     r8, aWdiSSLineD; "WDI: %s (%s):line-%d :- "
0x180002c67  mov     [rsp+8D0h+var_8A8], eax
0x180002c6b  lea     rcx, [rbp+7D0h+OutputString]; unsigned __int16 *
0x180002c6f  mov     ebx, 400h
0x180002c74  mov     [rsp+8D0h+var_8B0], r12
0x180002c79  mov     edx, ebx; unsigned __int64
0x180002c7b  mov     r9, r15
0x180002c7e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002c83  test    eax, eax
0x180002c85  js      loc_180002E2D
0x180002c8b  lea     esi, ds:2[rsi*2]
0x180002c92  mov     [rsp+8D0h+var_30], r13
0x180002c9a  mov     dword ptr [rsp+8D0h+var_898], esi
0x180002c9e  lea     r13d, ds:2[rdi*2]
0x180002ca6  lea     rcx, [rbp+7D0h+OutputString]
0x180002caa  mov     rax, r14
0x180002cad  nop     dword ptr [rax]
0x180002cb0  inc     rax
0x180002cb3  cmp     word ptr [rcx+rax*2], 0
0x180002cb8  jnz     short loc_180002CB0
0x180002cba  lea     rdi, [rbp+7D0h+OutputString]
0x180002cbe  lea     rdi, [rdi+rax*2]
0x180002cc2  sub     rbx, rax
0x180002cc5  jz      loc_180002DA0
0x180002ccb  cmp     rbx, 7FFFFFFFh
0x180002cd2  jbe     short loc_180002CE7
0x180002cd4  xor     eax, eax
0x180002cd6  mov     [rdi], ax
0x180002cd9  cmp     rbx, 7FFFFFFFh
0x180002ce0  jbe     short loc_180002D1C
0x180002ce2  jmp     loc_180002DA0
0x180002ce7  mov     r8, [rbp+7D0h+Format]; Format
0x180002cee  lea     rsi, [rbx-1]
0x180002cf2  mov     rdx, rsi; BufferCount
0x180002cf5  lea     r9, [rbp+7D0h+Args]; Args
0x180002cfc  mov     rcx, rdi; Buffer
0x180002cff  call    cs:__imp__vsnwprintf
0x180002d05  test    eax, eax
0x180002d07  js      short loc_180002D12
0x180002d09  cdqe
0x180002d0b  cmp     rax, rsi
0x180002d0e  ja      short loc_180002D12
0x180002d10  jnz     short loc_180002D18
0x180002d12  xor     eax, eax
0x180002d14  mov     [rdi+rsi*2], ax
0x180002d18  mov     esi, dword ptr [rsp+8D0h+var_898]
0x180002d1c  mov     rcx, rbx
0x180002d1f  mov     rax, rdi
0x180002d22  cmp     word ptr [rax], 0
0x180002d26  jz      short loc_180002D32
0x180002d28  add     rax, 2
0x180002d2c  sub     rcx, 1
0x180002d30  jnz     short loc_180002D22
0x180002d32  xor     r8d, r8d
0x180002d35  mov     rax, rbx
0x180002d38  sub     rax, rcx
0x180002d3b  test    rcx, rcx
0x180002d3e  cmovnz  r8, rax
0x180002d42  jz      short loc_180002DA0
0x180002d44  lea     rdx, asc_180013B24; "\n"
0x180002d4b  mov     ecx, 7FFFFFFEh
0x180002d50  lea     rax, [rdi+r8*2]
0x180002d54  sub     rbx, r8
0x180002d57  jz      short loc_180002D84
0x180002d59  nop     dword ptr [rax+00000000h]
0x180002d60  test    rcx, rcx
0x180002d63  jz      short loc_180002D84
0x180002d65  movzx   r8d, word ptr [rdx]
0x180002d69  test    r8w, r8w
0x180002d6d  jz      short loc_180002D84
0x180002d6f  mov     [rax], r8w
0x180002d73  add     rdx, 2
0x180002d77  add     rax, 2
0x180002d7b  dec     rcx
0x180002d7e  sub     rbx, 1
0x180002d82  jnz     short loc_180002D60
0x180002d84  test    rbx, rbx
0x180002d87  lea     rcx, [rax-2]
0x180002d8b  cmovnz  rcx, rax
0x180002d8f  xor     eax, eax
0x180002d91  mov     [rcx], ax
0x180002d94  nop     dword ptr [rax+00h]
0x180002d98  nop     dword ptr [rax+rax+00000000h]
0x180002da0  cmp     word ptr [rdi+r14*2+2], 0
0x180002da7  lea     r14, [r14+1]
0x180002dab  jnz     short loc_180002DA0
0x180002dad  lea     rcx, [rbp+7D0h+OutputString]; lpOutputString
0x180002db1  call    cs:__imp_OutputDebugStringW
0x180002db7  mov     rcx, cs:g_hETW; RegHandle
0x180002dbe  lea     rax, [rsp+8D0h+var_8A0]
0x180002dc3  mov     qword ptr [rsp+8D0h+var_878+8], rax
0x180002dc8  lea     r9, [rsp+8D0h+UserData]; UserData
0x180002dcd  lea     eax, ds:2[r14*2]
0x180002dd5  mov     qword ptr [rsp+8D0h+UserData], r15
0x180002dda  mov     r8d, 4; UserDataCount
0x180002de0  mov     dword ptr [rsp+8D0h+var_858], eax
0x180002de4  lea     rdx, WDI_DPS_EVENT_DEBUG; EventDescriptor
0x180002deb  mov     dword ptr [rsp+8D0h+UserData+8], r13d
0x180002df0  mov     dword ptr [rsp+8D0h+UserData+0Ch], 0
0x180002df8  mov     qword ptr [rsp+8D0h+UserData+10h], r12
0x180002dfd  mov     dword ptr [rsp+8D0h+var_878], esi
0x180002e01  mov     dword ptr [rsp+8D0h+var_878+4], 0
0x180002e09  mov     qword ptr [rsp+8D0h+var_868], 4
0x180002e12  mov     qword ptr [rsp+8D0h+var_868+8], rdi
0x180002e17  mov     dword ptr [rsp+8D0h+var_858+4], 0
0x180002e1f  call    cs:__imp_EventWrite
0x180002e25  mov     r13, [rsp+8D0h+var_30]
0x180002e2d  mov     rdi, [rsp+8D0h+var_28]
0x180002e35  mov     rsi, [rsp+8D0h+var_20]
0x180002e3d  mov     r14, [rsp+8D0h+var_38]
0x180002e45  mov     rcx, [rbp+7D0h+var_50]
0x180002e4c  xor     rcx, rsp; StackCookie
0x180002e4f  call    __security_check_cookie
0x180002e54  add     rsp, 8B8h
0x180002e5b  pop     r15
0x180002e5d  pop     r12
0x180002e5f  pop     rbx
0x180002e60  pop     rbp
0x180002e61  retn
0x180002e62  mov     eax, ebx
0x180002e64  jmp     short loc_180002E45
```
