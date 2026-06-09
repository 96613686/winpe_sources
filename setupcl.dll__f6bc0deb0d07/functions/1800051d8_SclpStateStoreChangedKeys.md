# SclpStateStoreChangedKeys

- ea: `0x1800051d8`
- end: `0x180005403`
- name: `SclpStateStoreChangedKeys`
- size: `555`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, void *, const WCHAR *, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x180004428`

## callees

- `0x18000154c`
- `0x180004f5c`
- `0x1800051d8`
- `0x180007ac4`
- `0x180008d44`
- `0x18000a334`
- `0x1800153c8`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180005228`
- `ntdll!RtlInitUnicodeString` at `0x180005268`
- `ntdll!RtlInitUnicodeString` at `0x180005228`
- `ntdll!RtlInitUnicodeString` at `0x180005268`
- `ntdll!NtClose` at `0x1800052ae`
- `ntdll!NtClose` at `0x1800053a5`
- `ntdll!NtClose` at `0x1800053b4`
- `ntdll!NtClose` at `0x1800052ae`
- `ntdll!NtClose` at `0x1800053a5`
- `ntdll!NtClose` at `0x1800053b4`
- `ntdll!RtlFreeHeap` at `0x1800053d1`
- `ntdll!RtlFreeHeap` at `0x1800053ee`
- `ntdll!RtlFreeHeap` at `0x1800053d1`
- `ntdll!RtlFreeHeap` at `0x1800053ee`

## string_xrefs

- `0x180005327`: `System32\config`

## pseudocode

```c
__int64 __fastcall SclpStateStoreChangedKeys(__int64 a1, const wchar_t *a2, void *a3, const WCHAR *a4, _QWORD *a5)
{
  WCHAR *v6; // rdi
  __int64 v9; // rdx
  int v10; // ebx
  _QWORD *v11; // rsi
  __int64 v12; // r8
  int v13; // eax
  wchar_t *v14; // rax
  wchar_t *v15; // rsi
  int v16; // eax
  __int64 v17; // rdx
  HANDLE Handle; // [rsp+30h] [rbp-38h] BYREF
  HANDLE v20; // [rsp+38h] [rbp-30h] BYREF
  WCHAR *v21; // [rsp+40h] [rbp-28h] BYREF
  __int64 v22; // [rsp+48h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-18h] BYREF
  ULONG v24; // [rsp+A0h] [rbp+38h] BYREF
  int v25; // [rsp+A4h] [rbp+3Ch]

  v25 = HIDWORD(a1);
  v22 = 0;
  v20 = 0;
  v6 = 0;
  Handle = 0;
  v21 = 0;
  v24 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a4);
  v10 = SclCreateKeyEx(a3, &DestinationString, 0x20006u, 0, 0, &v20);
  if ( v10 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"ChangedKeys");
    v10 = SclCreateKeyEx(v20, &DestinationString, 0x20006u, 0, &v24, &Handle);
    if ( v10 >= 0 && v24 == 2 )
    {
      v10 = SclRegDeleteKey(Handle);
      NtClose(Handle);
      Handle = 0;
      if ( v10 >= 0 )
        v10 = SclCreateKeyEx(v20, &DestinationString, 0x20006u, 0, &v24, &Handle);
    }
  }
  v11 = (_QWORD *)*a5;
  if ( v10 >= 0 )
  {
    do
    {
      if ( !v11 )
        break;
      v12 = v11[1];
      LODWORD(a5) = 1;
      v13 = SclRegSetValue(Handle, v9, v12, &a5, 4, 4);
      v11 = (_QWORD *)*v11;
      v10 = v13;
    }
    while ( v13 >= 0 );
  }
  v14 = BuildPathMulti(3u, a2, L"System32\\config", a4);
  v15 = v14;
  if ( v14 )
  {
    if ( v10 >= 0 )
    {
      v16 = SclDosPathToNtPath((__int64)v14, &v21);
      v6 = v21;
      v10 = v16;
      if ( v16 >= 0 )
      {
        v10 = SclpFileGetLastWriteTime(v21, &v22);
        if ( v10 >= 0 )
          v10 = SclRegSetValue(v20, v17, L"ChangeTag", &v22, 8, 11);
      }
    }
  }
  else
  {
    v10 = -1073741801;
  }
  if ( Handle )
    NtClose(Handle);
  if ( v20 )
    NtClose(v20);
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  if ( v15 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800051d8  mov     [rsp-30h+arg_0], rcx
0x1800051dd  push    rbp
0x1800051de  push    rbx
0x1800051df  push    rsi
0x1800051e0  push    rdi
0x1800051e1  push    r14
0x1800051e3  push    r15
0x1800051e5  mov     rbp, rsp
0x1800051e8  sub     rsp, 68h
0x1800051ec  mov     r15, rdx
0x1800051ef  mov     [rbp+var_20], 0
0x1800051f7  xorps   xmm0, xmm0
0x1800051fa  mov     [rbp+var_30], 0
0x180005202  xor     edi, edi
0x180005204  mov     [rbp+Handle], 0
0x18000520c  mov     rdx, r9; SourceString
0x18000520f  mov     [rbp+var_28], rdi
0x180005213  lea     rcx, [rbp+DestinationString]; DestinationString
0x180005217  mov     dword ptr [rbp+arg_0], 0
0x18000521e  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180005222  mov     r14, r9
0x180005225  mov     rbx, r8
0x180005228  call    cs:__imp_RtlInitUnicodeString
0x18000522e  lea     rax, [rbp+var_30]
0x180005232  mov     esi, 20006h
0x180005237  mov     [rsp+68h+var_40], rax
0x18000523c  lea     rdx, [rbp+DestinationString]
0x180005240  xor     r9d, r9d
0x180005243  mov     [rsp+68h+var_48], rdi
0x180005248  mov     r8d, esi
0x18000524b  mov     rcx, rbx
0x18000524e  call    SclCreateKeyEx
0x180005253  mov     ebx, eax
0x180005255  test    eax, eax
0x180005257  js      loc_1800052E3
0x18000525d  lea     rdx, SourceString; "ChangedKeys"
0x180005264  lea     rcx, [rbp+DestinationString]; DestinationString
0x180005268  call    cs:__imp_RtlInitUnicodeString
0x18000526e  mov     rcx, [rbp+var_30]
0x180005272  lea     rax, [rbp+Handle]
0x180005276  mov     [rsp+68h+var_40], rax
0x18000527b  lea     rdx, [rbp+DestinationString]
0x18000527f  lea     rax, [rbp+arg_0]
0x180005283  xor     r9d, r9d
0x180005286  mov     r8d, esi
0x180005289  mov     [rsp+68h+var_48], rax
0x18000528e  call    SclCreateKeyEx
0x180005293  mov     ebx, eax
0x180005295  test    eax, eax
0x180005297  js      short loc_1800052E3
0x180005299  cmp     dword ptr [rbp+arg_0], 2
0x18000529d  jnz     short loc_1800052E3
0x18000529f  mov     rcx, [rbp+Handle]; Handle
0x1800052a3  call    SclRegDeleteKey
0x1800052a8  mov     rcx, [rbp+Handle]; Handle
0x1800052ac  mov     ebx, eax
0x1800052ae  call    cs:__imp_NtClose
0x1800052b4  mov     [rbp+Handle], rdi
0x1800052b8  test    ebx, ebx
0x1800052ba  js      short loc_1800052E3
0x1800052bc  mov     rcx, [rbp+var_30]
0x1800052c0  lea     rax, [rbp+Handle]
0x1800052c4  mov     [rsp+68h+var_40], rax
0x1800052c9  lea     rdx, [rbp+DestinationString]
0x1800052cd  lea     rax, [rbp+arg_0]
0x1800052d1  xor     r9d, r9d
0x1800052d4  mov     r8d, esi
0x1800052d7  mov     [rsp+68h+var_48], rax
0x1800052dc  call    SclCreateKeyEx
0x1800052e1  mov     ebx, eax
0x1800052e3  mov     rax, [rbp+arg_20]
0x1800052e7  mov     rsi, [rax]
0x1800052ea  test    ebx, ebx
0x1800052ec  js      short loc_180005324
0x1800052ee  test    rsi, rsi
0x1800052f1  jz      short loc_180005324
0x1800052f3  mov     r8, [rsi+8]
0x1800052f7  lea     r9, [rbp+arg_20]
0x1800052fb  mov     rcx, [rbp+Handle]
0x1800052ff  mov     dword ptr [rsp+68h+var_40], 4
0x180005307  mov     dword ptr [rsp+68h+var_48], 4
0x18000530f  mov     dword ptr [rbp+arg_20], 1
0x180005316  call    SclRegSetValue
0x18000531b  mov     rsi, [rsi]
0x18000531e  mov     ebx, eax
0x180005320  test    eax, eax
0x180005322  jns     short loc_1800052EE
0x180005324  mov     r9, r14
0x180005327  lea     r8, aSystem32Config; "System32\\config"
0x18000532e  mov     rdx, r15
0x180005331  mov     ecx, 3
0x180005336  call    BuildPathMulti
0x18000533b  mov     rsi, rax
0x18000533e  test    rax, rax
0x180005341  jnz     short loc_18000534A
0x180005343  mov     ebx, 0C0000017h
0x180005348  jmp     short loc_18000539C
0x18000534a  test    ebx, ebx
0x18000534c  js      short loc_18000539C
0x18000534e  lea     rdx, [rbp+var_28]
0x180005352  mov     rcx, rsi
0x180005355  call    SclDosPathToNtPath
0x18000535a  mov     rdi, [rbp+var_28]
0x18000535e  mov     ebx, eax
0x180005360  test    eax, eax
0x180005362  js      short loc_18000539C
0x180005364  lea     rdx, [rbp+var_20]
0x180005368  mov     rcx, rdi
0x18000536b  call    SclpFileGetLastWriteTime
0x180005370  mov     ebx, eax
0x180005372  test    eax, eax
0x180005374  js      short loc_18000539C
0x180005376  mov     rcx, [rbp+var_30]
0x18000537a  lea     r9, [rbp+var_20]
0x18000537e  mov     dword ptr [rsp+68h+var_40], 0Bh
0x180005386  lea     r8, aChangetag; "ChangeTag"
0x18000538d  mov     dword ptr [rsp+68h+var_48], 8
0x180005395  call    SclRegSetValue
0x18000539a  mov     ebx, eax
0x18000539c  mov     rcx, [rbp+Handle]; Handle
0x1800053a0  test    rcx, rcx
0x1800053a3  jz      short loc_1800053AB
0x1800053a5  call    cs:__imp_NtClose
0x1800053ab  mov     rcx, [rbp+var_30]; Handle
0x1800053af  test    rcx, rcx
0x1800053b2  jz      short loc_1800053BA
0x1800053b4  call    cs:__imp_NtClose
0x1800053ba  test    rdi, rdi
0x1800053bd  jz      short loc_1800053D7
0x1800053bf  mov     rcx, gs:60h
0x1800053c8  mov     r8, rdi; P
0x1800053cb  xor     edx, edx; Flags
0x1800053cd  mov     rcx, [rcx+30h]; HeapHandle
0x1800053d1  call    cs:__imp_RtlFreeHeap
0x1800053d7  test    rsi, rsi
0x1800053da  jz      short loc_1800053F4
0x1800053dc  mov     rcx, gs:60h
0x1800053e5  mov     r8, rsi; P
0x1800053e8  xor     edx, edx; Flags
0x1800053ea  mov     rcx, [rcx+30h]; HeapHandle
0x1800053ee  call    cs:__imp_RtlFreeHeap
0x1800053f4  mov     eax, ebx
0x1800053f6  add     rsp, 68h
0x1800053fa  pop     r15
0x1800053fc  pop     r14
0x1800053fe  pop     rdi
0x1800053ff  pop     rsi
0x180005400  pop     rbx
0x180005401  pop     rbp
0x180005402  retn
```
