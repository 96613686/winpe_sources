# ConvertStringSidToSidW

- ea: `0x180008010`
- end: `0x180008215`
- name: `ConvertStringSidToSidW`
- size: `517`
- prototype: `BOOL __stdcall(LPCWSTR StringSid, PSID *Sid)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001a2a8`
- `0x1800204c8`

## callees

- `0x180004f20`
- `0x180008010`
- `0x180008220`

## import_xrefs

- `ntdll!RtlCopySid` at `0x1800081a0`
- `ntdll!RtlCopySid` at `0x1800081a0`
- `ntdll!RtlNtStatusToDosError` at `0x1800080c8`
- `ntdll!RtlNtStatusToDosError` at `0x1800081a8`
- `ntdll!RtlNtStatusToDosError` at `0x1800080c8`
- `ntdll!RtlNtStatusToDosError` at `0x1800081a8`
- `ntdll!RtlLengthSid` at `0x180008173`
- `ntdll!RtlLengthSid` at `0x180008173`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008039`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008068`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000809f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800080d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000813c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008156`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008039`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008068`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000809f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800080d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000813c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008156`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008182`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008182`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000815f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800081be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000820a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000815f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800081be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000820a`

## pseudocode

```c
BOOL __stdcall ConvertStringSidToSidW(LPCWSTR StringSid, PSID *Sid)
{
  NTSTATUS v5; // eax
  __int64 v6; // rax
  BOOL v7; // esi
  DWORD v8; // eax
  DWORD LastError; // r14d
  __int64 *v10; // rax
  __int64 *v11; // rbp
  void *v12; // rdx
  __int64 v13; // rax
  DWORD v14; // ecx
  ULONG v15; // ebx
  HLOCAL v16; // rax
  NTSTATUS v17; // eax
  ULONG v18; // ebx
  __int64 v19; // rax
  HLOCAL hMem; // [rsp+70h] [rbp+8h] BYREF
  __int64 v21; // [rsp+80h] [rbp+18h] BYREF

  v21 = 0;
  hMem = 0;
  if ( StringSid && Sid )
  {
    v5 = LocalpConvertStringSidToSid(StringSid, Sid, &v21);
    if ( v5 < 0 )
    {
      v8 = RtlNtStatusToDosError(v5);
      SetLastError(v8);
      v7 = 0;
      LastError = GetLastError();
      v10 = LookupSidInTable((wchar_t *)StringSid, 0, 0, 0, 0, 0, &hMem);
      v11 = v10;
      if ( v10 && (v12 = (void *)v10[2]) != 0 )
      {
        v13 = -1;
        do
          ++v13;
        while ( StringSid[v13] );
        if ( v13 == *((_DWORD *)v11 + 3) )
        {
          v15 = RtlLengthSid(v12);
          v16 = LocalAlloc(0x40u, v15);
          *Sid = v16;
          if ( v16 )
          {
            v17 = RtlCopySid(v15, v16, (PSID)v11[2]);
            v18 = RtlNtStatusToDosError(v17);
            if ( v18 )
            {
              LocalFree(*Sid);
              *Sid = 0;
            }
            else
            {
              v7 = 1;
            }
            v14 = v18;
          }
          else
          {
            v14 = 8;
          }
        }
        else
        {
          v14 = 1337;
        }
      }
      else
      {
        if ( !hMem )
          goto LABEL_31;
        v19 = -1;
        do
          ++v19;
        while ( StringSid[v19] );
        if ( v19 == 2 )
        {
          *Sid = hMem;
          v7 = 1;
          v14 = 0;
          hMem = 0;
        }
        else
        {
LABEL_31:
          v14 = LastError;
        }
      }
      SetLastError(v14);
    }
    else
    {
      SetLastError(0);
      v6 = -1;
      do
        ++v6;
      while ( StringSid[v6] );
      if ( (unsigned int)((v21 - (__int64)StringSid) >> 1) == v6 )
      {
        v7 = 1;
        SetLastError(0);
      }
      else
      {
        SetLastError(0x539u);
        LocalFree(*Sid);
        *Sid = 0;
        v7 = 0;
      }
    }
    if ( hMem )
      LocalFree(hMem);
    return v7;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x180008010  push    rbx
0x180008012  push    rdi
0x180008013  push    r15
0x180008015  sub     rsp, 50h
0x180008019  xor     r15d, r15d
0x18000801c  mov     rdi, rdx
0x18000801f  mov     [rsp+68h+arg_10], r15
0x180008027  mov     rbx, rcx
0x18000802a  mov     [rsp+68h+hMem], r15
0x18000802f  test    rcx, rcx
0x180008032  jnz     short loc_18000804B
0x180008034  mov     ecx, 57h ; 'W'; dwErrCode
0x180008039  call    cs:__imp_SetLastError
0x18000803f  mov     eax, r15d
0x180008042  add     rsp, 50h
0x180008046  pop     r15
0x180008048  pop     rdi
0x180008049  pop     rbx
0x18000804a  retn
0x18000804b  test    rdi, rdi
0x18000804e  jz      short loc_180008034
0x180008050  lea     r8, [rsp+68h+arg_10]
0x180008058  mov     [rsp+68h+var_20], rsi
0x18000805d  call    LocalpConvertStringSidToSid
0x180008062  test    eax, eax
0x180008064  js      short loc_1800080BC
0x180008066  xor     ecx, ecx; dwErrCode
0x180008068  call    cs:__imp_SetLastError
0x18000806e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180008075  inc     rax
0x180008078  cmp     [rbx+rax*2], r15w
0x18000807d  jnz     short loc_180008075
0x18000807f  mov     rcx, [rsp+68h+arg_10]
0x180008087  sub     rcx, rbx
0x18000808a  sar     rcx, 1
0x18000808d  mov     ecx, ecx
0x18000808f  cmp     rcx, rax
0x180008092  jnz     loc_180008151
0x180008098  xor     ecx, ecx; dwErrCode
0x18000809a  mov     esi, 1
0x18000809f  call    cs:__imp_SetLastError
0x1800080a5  mov     rcx, [rsp+68h+hMem]; hMem
0x1800080aa  test    rcx, rcx
0x1800080ad  jnz     loc_18000820A
0x1800080b3  mov     eax, esi
0x1800080b5  mov     rsi, [rsp+68h+var_20]
0x1800080ba  jmp     short loc_180008042
0x1800080bc  mov     [rsp+68h+arg_8], rbp
0x1800080c1  mov     ecx, eax; Status
0x1800080c3  mov     [rsp+68h+var_28], r14
0x1800080c8  call    cs:__imp_RtlNtStatusToDosError
0x1800080ce  mov     ecx, eax; dwErrCode
0x1800080d0  call    cs:__imp_SetLastError
0x1800080d6  mov     esi, r15d
0x1800080d9  call    cs:__imp_GetLastError
0x1800080df  xor     r9d, r9d
0x1800080e2  xor     r8d, r8d
0x1800080e5  mov     r14d, eax
0x1800080e8  xor     edx, edx; Sid
0x1800080ea  lea     rax, [rsp+68h+hMem]
0x1800080ef  mov     rcx, rbx; String1
0x1800080f2  mov     [rsp+68h+var_38], rax; __int64
0x1800080f7  mov     [rsp+68h+var_40], sil; char
0x1800080fc  mov     [rsp+68h+var_48], r15; __int64
0x180008101  call    LookupSidInTable
0x180008106  mov     rbp, rax
0x180008109  test    rax, rax
0x18000810c  jz      loc_1800081CE
0x180008112  mov     rdx, [rax+10h]
0x180008116  test    rdx, rdx
0x180008119  jz      loc_1800081CE
0x18000811f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180008126  inc     rax
0x180008129  cmp     [rbx+rax*2], si
0x18000812d  jnz     short loc_180008126
0x18000812f  mov     ecx, [rbp+0Ch]
0x180008132  cmp     rax, rcx
0x180008135  jz      short loc_180008170
0x180008137  mov     ecx, 539h; dwErrCode
0x18000813c  call    cs:__imp_SetLastError
0x180008142  mov     rbp, [rsp+68h+arg_8]
0x180008147  mov     r14, [rsp+68h+var_28]
0x18000814c  jmp     loc_1800080A5
0x180008151  mov     ecx, 539h; dwErrCode
0x180008156  call    cs:__imp_SetLastError
0x18000815c  mov     rcx, [rdi]; hMem
0x18000815f  call    cs:__imp_LocalFree
0x180008165  mov     [rdi], r15
0x180008168  mov     esi, r15d
0x18000816b  jmp     loc_1800080A5
0x180008170  mov     rcx, rdx; Sid
0x180008173  call    cs:__imp_RtlLengthSid
0x180008179  mov     edx, eax; uBytes
0x18000817b  mov     ecx, 40h ; '@'; uFlags
0x180008180  mov     ebx, eax
0x180008182  call    cs:__imp_LocalAlloc
0x180008188  mov     [rdi], rax
0x18000818b  test    rax, rax
0x18000818e  jnz     short loc_180008197
0x180008190  mov     ecx, 8
0x180008195  jmp     short loc_18000813C
0x180008197  mov     r8, [rbp+10h]; SourceSid
0x18000819b  mov     rdx, rax; DestinationSid
0x18000819e  mov     ecx, ebx; DestinationSidLength
0x1800081a0  call    cs:__imp_RtlCopySid
0x1800081a6  mov     ecx, eax; Status
0x1800081a8  call    cs:__imp_RtlNtStatusToDosError
0x1800081ae  mov     ebx, eax
0x1800081b0  test    eax, eax
0x1800081b2  jnz     short loc_1800081BB
0x1800081b4  mov     esi, 1
0x1800081b9  jmp     short loc_1800081C7
0x1800081bb  mov     rcx, [rdi]; hMem
0x1800081be  call    cs:__imp_LocalFree
0x1800081c4  mov     [rdi], r15
0x1800081c7  mov     ecx, ebx
0x1800081c9  jmp     loc_18000813C
0x1800081ce  mov     rcx, [rsp+68h+hMem]
0x1800081d3  test    rcx, rcx
0x1800081d6  jz      short loc_180008202
0x1800081d8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800081df  inc     rax
0x1800081e2  cmp     [rbx+rax*2], si
0x1800081e6  jnz     short loc_1800081DF
0x1800081e8  cmp     rax, 2
0x1800081ec  jnz     short loc_180008202
0x1800081ee  mov     [rdi], rcx
0x1800081f1  mov     esi, 1
0x1800081f6  xor     ecx, ecx
0x1800081f8  mov     [rsp+68h+hMem], r15
0x1800081fd  jmp     loc_18000813C
0x180008202  mov     ecx, r14d
0x180008205  jmp     loc_18000813C
0x18000820a  call    cs:__imp_LocalFree
0x180008210  jmp     loc_1800080B3
```
