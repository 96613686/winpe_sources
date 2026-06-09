# SpGetExtendedInformation

- ea: `0x180068380`
- end: `0x1800684bf`
- name: `SpGetExtendedInformation`
- size: `319`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180068380`
- `0x180091010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180068422`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180068435`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180068422`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180068435`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x1800683db`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x1800683db`
- `ntdll!RtlInitUnicodeString` at `0x180068448`
- `ntdll!RtlInitUnicodeString` at `0x180068448`

## string_xrefs

- `0x180068428`: `schannel.dll`

## pseudocode

```c
__int64 __fastcall SpGetExtendedInformation(int a1, __int64 *a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rdi
  __int64 v5; // rax
  const WCHAR *v6; // rbx
  UINT SystemWow64DirectoryW; // eax
  __int64 v8; // rax

  if ( a1 == 2 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64))(LsaTable + 40))(112);
    v4 = v8;
    if ( !v8 )
    {
      v3 = -2146893056;
      goto LABEL_16;
    }
    *(_DWORD *)v8 = 2;
    *(_DWORD *)(v8 + 8) = 14;
    *(_OWORD *)(v8 + 12) = xmmword_180099C38;
    *(_OWORD *)(v8 + 28) = xmmword_180099C48;
    *(_OWORD *)(v8 + 44) = xmmword_180099C58;
    *(_QWORD *)(v8 + 60) = 0xC1007600000075LL;
    goto LABEL_14;
  }
  if ( a1 == 4 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64))(LsaTable + 40))(576);
    v4 = v5;
    if ( !v5 )
    {
      v3 = -1073741670;
      goto LABEL_16;
    }
    v6 = (const WCHAR *)(v5 + 56);
    SystemWow64DirectoryW = GetSystemWow64DirectoryW((LPWSTR)(v5 + 56), 0x104u);
    if ( !SystemWow64DirectoryW )
    {
      v3 = -2146893054;
LABEL_8:
      (*(void (__fastcall **)(__int64))(LsaTable + 48))(v4);
      goto LABEL_16;
    }
    if ( (unsigned __int64)(SystemWow64DirectoryW + 1) + 12 >= 0x104 )
    {
      v3 = -1073741670;
      goto LABEL_8;
    }
    _o_wcscat_s(v6, 260, L"\\");
    _o_wcscat_s(v6, 260, L"schannel.dll");
    *(_DWORD *)v4 = 4;
    RtlInitUnicodeString((PUNICODE_STRING)(v4 + 8), v6);
LABEL_14:
    v3 = 0;
    goto LABEL_16;
  }
  v3 = -2146893054;
  v4 = 0;
LABEL_16:
  *a2 = v4;
  return v3;
}

```

## disassembly

```asm
0x180068380  push    rbx
0x180068382  push    rbp
0x180068383  push    rsi
0x180068384  push    rdi
0x180068385  sub     rsp, 28h
0x180068389  mov     rsi, rdx
0x18006838c  cmp     ecx, 2
0x18006838f  jz      loc_180068450
0x180068395  cmp     ecx, 4
0x180068398  jz      short loc_1800683A6
0x18006839a  mov     ebx, 80090302h
0x18006839f  xor     edi, edi
0x1800683a1  jmp     loc_1800684B1
0x1800683a6  mov     rax, cs:LsaTable
0x1800683ad  mov     ecx, 240h
0x1800683b2  mov     rax, [rax+28h]
0x1800683b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800683bb  mov     rdi, rax
0x1800683be  test    rax, rax
0x1800683c1  jnz     short loc_1800683CD
0x1800683c3  mov     ebx, 0C000009Ah
0x1800683c8  jmp     loc_1800684B1
0x1800683cd  lea     rbx, [rax+38h]
0x1800683d1  mov     ebp, 104h
0x1800683d6  mov     edx, ebp; uSize
0x1800683d8  mov     rcx, rbx; lpBuffer
0x1800683db  call    cs:__imp_GetSystemWow64DirectoryW
0x1800683e1  test    eax, eax
0x1800683e3  jnz     short loc_180068402
0x1800683e5  mov     ebx, 80090302h
0x1800683ea  mov     rax, cs:LsaTable
0x1800683f1  mov     rcx, rdi
0x1800683f4  mov     rax, [rax+30h]
0x1800683f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800683fd  jmp     loc_1800684B1
0x180068402  lea     ecx, [rax+1]
0x180068405  add     rcx, 0Ch
0x180068409  cmp     rcx, rbp
0x18006840c  jb      short loc_180068415
0x18006840e  mov     ebx, 0C000009Ah
0x180068413  jmp     short loc_1800683EA
0x180068415  lea     r8, Source; "\\"
0x18006841c  mov     rdx, rbp
0x18006841f  mov     rcx, rbx
0x180068422  call    cs:__imp__o_wcscat_s
0x180068428  lea     r8, aSchannelDll_0; "schannel.dll"
0x18006842f  mov     rdx, rbp
0x180068432  mov     rcx, rbx
0x180068435  call    cs:__imp__o_wcscat_s
0x18006843b  lea     rcx, [rdi+8]; DestinationString
0x18006843f  mov     dword ptr [rdi], 4
0x180068445  mov     rdx, rbx; SourceString
0x180068448  call    cs:__imp_RtlInitUnicodeString
0x18006844e  jmp     short loc_1800684A8
0x180068450  mov     rax, cs:LsaTable
0x180068457  mov     ecx, 70h ; 'p'
0x18006845c  mov     rax, [rax+28h]
0x180068460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068465  mov     rdi, rax
0x180068468  test    rax, rax
0x18006846b  jz      short loc_1800684AC
0x18006846d  mov     dword ptr [rax], 2
0x180068473  mov     dword ptr [rax+8], 0Eh
0x18006847a  movups  xmm0, cs:xmmword_180099C38
0x180068481  movups  xmmword ptr [rax+0Ch], xmm0
0x180068485  movups  xmm1, cs:xmmword_180099C48
0x18006848c  movups  xmmword ptr [rax+1Ch], xmm1
0x180068490  movups  xmm0, cs:xmmword_180099C58
0x180068497  movups  xmmword ptr [rax+2Ch], xmm0
0x18006849b  movsd   xmm1, cs:qword_180099C68
0x1800684a3  movsd   qword ptr [rax+3Ch], xmm1
0x1800684a8  xor     ebx, ebx
0x1800684aa  jmp     short loc_1800684B1
0x1800684ac  mov     ebx, 80090300h
0x1800684b1  mov     [rsi], rdi
0x1800684b4  mov     eax, ebx
0x1800684b6  add     rsp, 28h
0x1800684ba  pop     rdi
0x1800684bb  pop     rsi
0x1800684bc  pop     rbp
0x1800684bd  pop     rbx
0x1800684be  retn
```
