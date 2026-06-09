# CopyAliasStructure(_ALIAS_GENERAL_INFORMATION * const,_ALIAS_GENERAL_INFORMATION *)

- ea: `0x18000fce4`
- end: `0x18000fdf4`
- name: `?CopyAliasStructure@@YAJQEAU_ALIAS_GENERAL_INFORMATION@@PEAU1@@Z`
- size: `272`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, PUNICODE_STRING DestinationString)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180011e80`
- `0x180014d90`

## callees

- `0x18000b290`
- `0x18000fce4`
- `0x180012f18`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000fd3b`
- `ntdll!RtlInitUnicodeString` at `0x18000fd7a`
- `ntdll!RtlInitUnicodeString` at `0x18000fd3b`
- `ntdll!RtlInitUnicodeString` at `0x18000fd7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fda3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fdac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fda3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fdac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fd13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fd4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fd13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fd4d`

## pseudocode

```c
__int64 __fastcall CopyAliasStructure(struct _UNICODE_STRING *a1, char *DestinationString)
{
  WCHAR *v2; // rsi
  SIZE_T v5; // rbx
  unsigned __int16 *v6; // rax
  WCHAR *v7; // r11
  int v8; // ebx
  SIZE_T v9; // r14
  unsigned __int16 *v10; // rax
  int v11; // eax

  v2 = 0;
  if ( !a1 || !DestinationString )
  {
    v8 = -2147467261;
    goto LABEL_11;
  }
  v5 = (unsigned int)a1->Length + 2;
  v6 = (unsigned __int16 *)CoTaskMemAlloc(v5);
  v7 = v6;
  if ( v6 )
  {
    v8 = CopyUstrToPstr(a1, v6, v5);
    if ( v8 >= 0 )
    {
      RtlInitUnicodeString((PUNICODE_STRING)DestinationString, v7);
      v9 = (unsigned int)LOWORD(a1[1].Buffer) + 2;
      v10 = (unsigned __int16 *)CoTaskMemAlloc(v9);
      v2 = v10;
      if ( !v10 )
      {
        v8 = -2147024882;
        goto LABEL_11;
      }
      v11 = CopyUstrToPstr((struct _UNICODE_STRING *)((char *)a1 + 24), v10, v9);
      v7 = 0;
      v8 = v11;
      if ( v11 >= 0 )
      {
        RtlInitUnicodeString((PUNICODE_STRING)(DestinationString + 24), v2);
        v2 = 0;
        *((_DWORD *)DestinationString + 4) = *(_DWORD *)&a1[1].Length;
LABEL_11:
        v7 = 0;
      }
    }
  }
  else
  {
    v8 = -2147024882;
  }
  CoTaskMemFree(v7);
  CoTaskMemFree(v2);
  if ( v8 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000fce4  push    rbx
0x18000fce6  push    rbp
0x18000fce7  push    rsi
0x18000fce8  push    rdi
0x18000fce9  push    r14
0x18000fceb  sub     rsp, 20h
0x18000fcef  xor     esi, esi
0x18000fcf1  mov     rbp, rdx
0x18000fcf4  mov     rdi, rcx
0x18000fcf7  test    rcx, rcx
0x18000fcfa  jz      loc_18000FD98
0x18000fd00  test    rdx, rdx
0x18000fd03  jz      loc_18000FD98
0x18000fd09  movzx   eax, word ptr [rcx]
0x18000fd0c  add     eax, 2
0x18000fd0f  mov     ecx, eax; cb
0x18000fd11  mov     ebx, eax
0x18000fd13  call    cs:__imp_CoTaskMemAlloc
0x18000fd19  mov     r11, rax
0x18000fd1c  test    rax, rax
0x18000fd1f  jz      short loc_18000FD91
0x18000fd21  mov     r8d, ebx; unsigned int
0x18000fd24  mov     rdx, rax; unsigned __int16 *
0x18000fd27  mov     rcx, rdi; struct _UNICODE_STRING *
0x18000fd2a  call    ?CopyUstrToPstr@@YAJQEAU_UNICODE_STRING@@PEAGK@Z; CopyUstrToPstr(_UNICODE_STRING * const,ushort *,ulong)
0x18000fd2f  mov     ebx, eax
0x18000fd31  test    eax, eax
0x18000fd33  js      short loc_18000FDA0
0x18000fd35  mov     rdx, r11; SourceString
0x18000fd38  mov     rcx, rbp; DestinationString
0x18000fd3b  call    cs:__imp_RtlInitUnicodeString
0x18000fd41  movzx   eax, word ptr [rdi+18h]
0x18000fd45  add     eax, 2
0x18000fd48  mov     ecx, eax; cb
0x18000fd4a  mov     r14d, eax
0x18000fd4d  call    cs:__imp_CoTaskMemAlloc
0x18000fd53  mov     rsi, rax
0x18000fd56  test    rax, rax
0x18000fd59  jz      short loc_18000FD8A
0x18000fd5b  mov     r8d, r14d; unsigned int
0x18000fd5e  lea     rcx, [rdi+18h]; struct _UNICODE_STRING *
0x18000fd62  mov     rdx, rax; unsigned __int16 *
0x18000fd65  call    ?CopyUstrToPstr@@YAJQEAU_UNICODE_STRING@@PEAGK@Z; CopyUstrToPstr(_UNICODE_STRING * const,ushort *,ulong)
0x18000fd6a  xor     r11d, r11d
0x18000fd6d  mov     ebx, eax
0x18000fd6f  test    eax, eax
0x18000fd71  js      short loc_18000FDA0
0x18000fd73  lea     rcx, [rbp+18h]; DestinationString
0x18000fd77  mov     rdx, rsi; SourceString
0x18000fd7a  call    cs:__imp_RtlInitUnicodeString
0x18000fd80  mov     eax, [rdi+10h]
0x18000fd83  xor     esi, esi
0x18000fd85  mov     [rbp+10h], eax
0x18000fd88  jmp     short loc_18000FD9D
0x18000fd8a  mov     ebx, 8007000Eh
0x18000fd8f  jmp     short loc_18000FD9D
0x18000fd91  mov     ebx, 8007000Eh
0x18000fd96  jmp     short loc_18000FDA0
0x18000fd98  mov     ebx, 80004003h
0x18000fd9d  xor     r11d, r11d
0x18000fda0  mov     rcx, r11; pv
0x18000fda3  call    cs:__imp_CoTaskMemFree
0x18000fda9  mov     rcx, rsi; pv
0x18000fdac  call    cs:__imp_CoTaskMemFree
0x18000fdb2  test    ebx, ebx
0x18000fdb4  jns     short loc_18000FDE7
0x18000fdb6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fdbd  lea     rax, WPP_GLOBAL_Control
0x18000fdc4  cmp     rcx, rax
0x18000fdc7  jz      short loc_18000FDE7
0x18000fdc9  test    byte ptr [rcx+1Ch], 2
0x18000fdcd  jz      short loc_18000FDE7
0x18000fdcf  mov     rcx, [rcx+10h]
0x18000fdd3  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x18000fdda  mov     edx, 24h ; '$'
0x18000fddf  mov     r9d, ebx
0x18000fde2  call    WPP_SF_d
0x18000fde7  mov     eax, ebx
0x18000fde9  add     rsp, 20h
0x18000fded  pop     r14
0x18000fdef  pop     rdi
0x18000fdf0  pop     rsi
0x18000fdf1  pop     rbp
0x18000fdf2  pop     rbx
0x18000fdf3  retn
```
