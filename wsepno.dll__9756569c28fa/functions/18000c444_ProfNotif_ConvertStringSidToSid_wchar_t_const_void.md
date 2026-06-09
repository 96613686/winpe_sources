# ProfNotif_ConvertStringSidToSid(wchar_t const *,void * *)

- ea: `0x18000c444`
- end: `0x18000c510`
- name: `?ProfNotif_ConvertStringSidToSid@@YAJPEB_WPEAPEAX@Z`
- size: `204`
- prototype: `int(const wchar_t *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007768`

## callees

- `0x180003b7c`
- `0x180003be0`
- `0x18000c444`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c46f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c46f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4d7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000c465`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000c465`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000c4cd`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000c4cd`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000c499`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000c499`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000c4ad`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000c4ad`

## pseudocode

```c
__int64 __fastcall ProfNotif_ConvertStringSidToSid(const wchar_t *a1, void **a2)
{
  signed int v3; // eax
  signed int v4; // ebx
  PSID v5; // rsi
  PSID v6; // rcx
  void *v7; // rdx
  DWORD LengthSid; // ebp
  int v9; // edx
  void *v10; // r9
  signed int LastError; // eax
  void *v12; // rdx
  PSID Sid; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 0;
  Sid = 0;
  if ( ConvertStringSidToSidW(a1, &Sid) )
  {
    v5 = Sid;
    v6 = Sid;
    *a2 = 0;
    if ( IsValidSid(v6) )
    {
      LengthSid = GetLengthSid(v5);
      v4 = ProfNotif_HeapAlloc(LengthSid, v9, a2, v10);
      if ( v4 >= 0 && !CopySid(LengthSid, *a2, v5) )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        ProfNotif_HeapFree(*a2, v12);
        *a2 = 0;
      }
    }
    else
    {
      v4 = -2147023559;
    }
    ProfNotif_HeapFree(Sid, v7);
  }
  else
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      return (unsigned __int16)v3 | 0x80070000;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000c444  push    rbx
0x18000c446  push    rbp
0x18000c447  push    rsi
0x18000c448  push    rdi
0x18000c449  sub     rsp, 28h
0x18000c44d  mov     rdi, rdx
0x18000c450  mov     qword ptr [rdx], 0
0x18000c457  lea     rdx, [rsp+48h+Sid]; Sid
0x18000c45c  mov     [rsp+48h+Sid], 0
0x18000c465  call    cs:__imp_ConvertStringSidToSidW
0x18000c46b  test    eax, eax
0x18000c46d  jnz     short loc_18000C48A
0x18000c46f  call    cs:__imp_GetLastError
0x18000c475  mov     ebx, eax
0x18000c477  test    eax, eax
0x18000c479  jle     loc_18000C505
0x18000c47f  movzx   ebx, ax
0x18000c482  or      ebx, 80070000h
0x18000c488  jmp     short loc_18000C505
0x18000c48a  mov     rsi, [rsp+48h+Sid]
0x18000c48f  mov     rcx, rsi; pSid
0x18000c492  mov     qword ptr [rdi], 0
0x18000c499  call    cs:__imp_IsValidSid
0x18000c49f  test    eax, eax
0x18000c4a1  jnz     short loc_18000C4AA
0x18000c4a3  mov     ebx, 80070539h
0x18000c4a8  jmp     short loc_18000C4FB
0x18000c4aa  mov     rcx, rsi; pSid
0x18000c4ad  call    cs:__imp_GetLengthSid
0x18000c4b3  mov     ecx, eax; dwBytes
0x18000c4b5  mov     r8, rdi; void **
0x18000c4b8  mov     ebp, eax
0x18000c4ba  call    ?ProfNotif_HeapAlloc@@YAJ_KHPEAPEAXPEAX@Z; ProfNotif_HeapAlloc(unsigned __int64,int,void * *,void *)
0x18000c4bf  mov     ebx, eax
0x18000c4c1  test    eax, eax
0x18000c4c3  js      short loc_18000C4FB
0x18000c4c5  mov     rdx, [rdi]; pDestinationSid
0x18000c4c8  mov     r8, rsi; pSourceSid
0x18000c4cb  mov     ecx, ebp; nDestinationSidLength
0x18000c4cd  call    cs:__imp_CopySid
0x18000c4d3  test    eax, eax
0x18000c4d5  jnz     short loc_18000C4FB
0x18000c4d7  call    cs:__imp_GetLastError
0x18000c4dd  mov     ebx, eax
0x18000c4df  test    eax, eax
0x18000c4e1  jle     short loc_18000C4EC
0x18000c4e3  movzx   ebx, ax
0x18000c4e6  or      ebx, 80070000h
0x18000c4ec  mov     rcx, [rdi]; lpMem
0x18000c4ef  call    ?ProfNotif_HeapFree@@YAJPEAX0@Z; ProfNotif_HeapFree(void *,void *)
0x18000c4f4  mov     qword ptr [rdi], 0
0x18000c4fb  mov     rcx, [rsp+48h+Sid]; lpMem
0x18000c500  call    ?ProfNotif_HeapFree@@YAJPEAX0@Z; ProfNotif_HeapFree(void *,void *)
0x18000c505  mov     eax, ebx
0x18000c507  add     rsp, 28h
0x18000c50b  pop     rdi
0x18000c50c  pop     rsi
0x18000c50d  pop     rbp
0x18000c50e  pop     rbx
0x18000c50f  retn
```
