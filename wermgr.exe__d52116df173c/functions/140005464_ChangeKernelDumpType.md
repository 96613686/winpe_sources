# ChangeKernelDumpType

- ea: `0x140005464`
- end: `0x140005606`
- name: `ChangeKernelDumpType`
- size: `418`
- prototype: `__int64 __fastcall(int, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140004e18`

## callees

- `0x14000162c`
- `0x140003200`
- `0x140005464`
- `0x14000a070`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400054c9`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400054c9`
- `wer!WerpReinitializeKernelCrashDump` at `0x140005509`
- `wer!WerpReinitializeKernelCrashDump` at `0x140005509`

## pseudocode

```c
__int64 __fastcall ChangeKernelDumpType(int a1, int *a2)
{
  LSTATUS v4; // eax
  signed int v5; // ebx
  __int64 v6; // rax
  int v7; // eax
  wil::details *lpData; // [rsp+20h] [rbp-69h]
  int cbData; // [rsp+28h] [rbp-61h]
  int Data; // [rsp+30h] [rbp-59h] BYREF
  signed int v11; // [rsp+38h] [rbp-51h] BYREF
  int v12; // [rsp+3Ch] [rbp-4Dh] BYREF
  __int64 v13; // [rsp+40h] [rbp-49h] BYREF
  char v14[32]; // [rsp+50h] [rbp-39h] BYREF
  __int64 *v15; // [rsp+70h] [rbp-19h]
  __int64 v16; // [rsp+78h] [rbp-11h]
  int *v17; // [rsp+80h] [rbp-9h]
  __int64 v18; // [rsp+88h] [rbp-1h]
  int *v19; // [rsp+90h] [rbp+7h]
  int v20; // [rsp+98h] [rbp+Fh]
  int v21; // [rsp+9Ch] [rbp+13h]
  signed int *v22; // [rsp+A0h] [rbp+17h]
  __int64 v23; // [rsp+A8h] [rbp+1Fh]
  wil::details::in1diag4 *retaddr; // [rsp+E8h] [rbp+5Fh]

  Data = a1;
  if ( ((a1 - 3) & 0xFFFFFFFB) != 0 )
    return 2147549183LL;
  v4 = RegSetKeyValueW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\CrashControl",
         L"CrashDumpEnabled",
         4u,
         &Data,
         4u);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 >= 0 )
  {
    v5 = WerpReinitializeKernelCrashDump();
    if ( (unsigned int)dword_14002C000 > 5
      && (qword_14002C010 & 0x400000000000LL) != 0
      && (qword_14002C018 & 0x400000000000LL) == qword_14002C018 )
    {
      v12 = Data;
      v22 = &v11;
      v11 = v5;
      v13 = 0x1000000;
      v23 = 4;
      if ( a2 )
      {
        v6 = -1;
        do
          ++v6;
        while ( *((_WORD *)a2 + v6) );
        v7 = 2 * v6 + 2;
      }
      else
      {
        a2 = &dword_1400241F4;
        v7 = 2;
      }
      v20 = v7;
      v19 = a2;
      v17 = &v12;
      v21 = 0;
      v15 = &v13;
      v18 = 4;
      v16 = 8;
      tlgWriteTransfer_EventWriteTransfer(&dword_14002C000, &word_140025E1E, 0, 0, 6, v14);
    }
  }
  else
  {
    LODWORD(lpData) = v5;
    wil::details::in1diag4::Return_Hr(
      retaddr,
      (void *)0x57E,
      (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
      "ChangeKernelDumpType",
      lpData,
      cbData);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140005464  push    rbp
0x140005466  push    rbx
0x140005467  push    rsi
0x140005468  push    rdi
0x140005469  lea     rbp, [rsp-3Fh]
0x14000546e  sub     rsp, 0C8h
0x140005475  mov     rax, cs:__security_cookie
0x14000547c  xor     rax, rsp
0x14000547f  mov     [rbp+57h+var_30], rax
0x140005483  lea     eax, [rcx-3]
0x140005486  mov     [rbp+57h+Data], ecx
0x140005489  mov     rdi, rdx
0x14000548c  test    eax, 0FFFFFFFBh
0x140005491  jz      short loc_14000549D
0x140005493  mov     eax, 8000FFFFh
0x140005498  jmp     loc_1400055EE
0x14000549d  lea     rax, [rbp+57h+Data]
0x1400054a1  mov     [rsp+0E0h+cbData], 4; int
0x1400054a9  mov     r9d, 4; dwType
0x1400054af  mov     [rsp+0E0h+lpData], rax; lpData
0x1400054b4  lea     r8, aCrashdumpenabl; "CrashDumpEnabled"
0x1400054bb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400054c2  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Cra"...
0x1400054c9  call    cs:__imp_RegSetKeyValueW
0x1400054cf  xor     esi, esi
0x1400054d1  mov     ebx, eax
0x1400054d3  test    eax, eax
0x1400054d5  jle     short loc_1400054E0
0x1400054d7  movzx   ebx, ax
0x1400054da  or      ebx, 80070000h
0x1400054e0  test    ebx, ebx
0x1400054e2  jns     short loc_140005509
0x1400054e4  mov     rcx, [rbp+5Fh]; this
0x1400054e8  lea     r9, aChangekerneldu; "ChangeKernelDumpType"
0x1400054ef  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x1400054f6  mov     dword ptr [rsp+0E0h+lpData], ebx; wil::details *
0x1400054fa  mov     edx, 57Eh; void *
0x1400054ff  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x140005504  jmp     loc_1400055EC
0x140005509  call    cs:__imp_WerpReinitializeKernelCrashDump
0x14000550f  mov     ecx, cs:dword_14002C000
0x140005515  mov     ebx, eax
0x140005517  cmp     ecx, 5
0x14000551a  jbe     loc_1400055EC
0x140005520  mov     rax, cs:qword_14002C018
0x140005527  mov     rdx, 400000000000h
0x140005531  mov     rcx, cs:qword_14002C010
0x140005538  test    rdx, rcx
0x14000553b  jz      loc_1400055EC
0x140005541  mov     rcx, rax
0x140005544  and     rcx, rdx
0x140005547  cmp     rcx, rax
0x14000554a  jnz     loc_1400055EC
0x140005550  mov     eax, [rbp+57h+Data]
0x140005553  mov     [rbp+57h+var_A4], eax
0x140005556  lea     rax, [rbp+57h+var_A8]
0x14000555a  mov     [rbp+57h+var_40], rax
0x14000555e  mov     [rbp+57h+var_A8], ebx
0x140005561  mov     [rbp+57h+var_A0], 1000000h
0x140005569  mov     [rbp+57h+var_38], 4
0x140005571  test    rdi, rdi
0x140005574  jz      short loc_14000558C
0x140005576  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000557a  inc     rax
0x14000557d  cmp     [rdi+rax*2], si
0x140005581  jnz     short loc_14000557A
0x140005583  lea     eax, ds:2[rax*2]
0x14000558a  jmp     short loc_140005598
0x14000558c  lea     rdi, dword_1400241F4
0x140005593  mov     eax, 2
0x140005598  mov     [rbp+57h+var_48], eax
0x14000559b  lea     rdx, word_140025E1E
0x1400055a2  lea     rax, [rbp+57h+var_A4]
0x1400055a6  mov     [rbp+57h+var_50], rdi
0x1400055aa  mov     [rbp+57h+var_60], rax
0x1400055ae  lea     rcx, dword_14002C000
0x1400055b5  lea     rax, [rbp+57h+var_A0]
0x1400055b9  mov     [rbp+57h+var_44], esi
0x1400055bc  mov     [rbp+57h+var_70], rax
0x1400055c0  xor     r9d, r9d
0x1400055c3  lea     rax, [rbp+57h+var_90]
0x1400055c7  mov     [rbp+57h+var_58], 4
0x1400055cf  mov     qword ptr [rsp+0E0h+cbData], rax
0x1400055d4  xor     r8d, r8d
0x1400055d7  mov     dword ptr [rsp+0E0h+lpData], 6
0x1400055df  mov     [rbp+57h+var_68], 8
0x1400055e7  call    _tlgWriteTransfer_EventWriteTransfer
0x1400055ec  mov     eax, ebx
0x1400055ee  mov     rcx, [rbp+57h+var_30]
0x1400055f2  xor     rcx, rsp; StackCookie
0x1400055f5  call    __security_check_cookie
0x1400055fa  add     rsp, 0C8h
0x140005601  pop     rdi
0x140005602  pop     rsi
0x140005603  pop     rbx
0x140005604  pop     rbp
0x140005605  retn
```
