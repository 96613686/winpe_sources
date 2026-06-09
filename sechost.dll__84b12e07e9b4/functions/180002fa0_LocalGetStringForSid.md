# LocalGetStringForSid

- ea: `0x180002fa0`
- end: `0x180003186`
- name: `LocalGetStringForSid`
- size: `486`
- prototype: `__int64 __usercall@<rax>(PSID Sid@<rcx>, __int64, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800015a0`
- `0x1800026b0`

## callees

- `0x180002fa0`
- `0x180004f20`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!wcscpy_s` at `0x180003045`
- `api-ms-win-core-crt-l1-1-0!wcscpy_s` at `0x180003045`
- `ntdll!RtlNtStatusToDosError` at `0x180003110`
- `ntdll!RtlNtStatusToDosError` at `0x180003110`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180003080`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180003080`
- `ntdll!RtlFreeUnicodeString` at `0x180003130`
- `ntdll!RtlFreeUnicodeString` at `0x180003152`
- `ntdll!RtlFreeUnicodeString` at `0x180003130`
- `ntdll!RtlFreeUnicodeString` at `0x180003152`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003118`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003138`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003118`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003138`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000311e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000311e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000301d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000309e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000301d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000309e`

## pseudocode

```c
__int64 __fastcall LocalGetStringForSid(PSID Sid, wchar_t **a2, _BYTE *a3, _BYTE *a4, __int64 a5, char a6)
{
  unsigned int v8; // ebp
  __int64 *v9; // rax
  __int64 *v10; // rdi
  unsigned int v11; // eax
  SIZE_T v12; // rbx
  wchar_t *v13; // rax
  const wchar_t *v14; // r8
  int v16; // ecx
  wchar_t *v17; // rax
  wchar_t *v18; // r8
  unsigned __int64 v19; // rdx
  PWSTR Buffer; // r9
  unsigned __int64 v21; // rax
  wchar_t *v22; // rcx
  DWORD v23; // eax
  _UNICODE_STRING UnicodeString; // [rsp+40h] [rbp-18h] BYREF
  PSID v25; // [rsp+60h] [rbp+8h] BYREF

  v25 = 0;
  if ( Sid && a2 )
  {
    v8 = 0;
    v9 = LookupSidInTable(0, Sid, a3, a4, a5, a6, &v25);
    v10 = v9;
    if ( v9 )
    {
      v11 = *((_DWORD *)v9 + 3);
      goto LABEL_5;
    }
    if ( v25 )
    {
      v11 = 2;
LABEL_5:
      v12 = 2LL * v11 + 2;
      v13 = (wchar_t *)LocalAlloc(0x40u, v12);
      *a2 = v13;
      if ( v13 )
      {
        if ( v10 )
          v14 = (const wchar_t *)v10 + 1;
        else
          v14 = L"SA";
        wcscpy_s(v13, v12 >> 1, v14);
      }
      else
      {
        return 8;
      }
      return v8;
    }
    UnicodeString = 0;
    v16 = RtlConvertSidToUnicodeString(&UnicodeString, Sid, 1u);
    if ( v16 >= 0 )
    {
      v17 = (wchar_t *)LocalAlloc(0x40u, UnicodeString.Length + 2LL);
      *a2 = v17;
      v18 = v17;
      if ( v17 )
      {
        v19 = ((unsigned __int64)UnicodeString.Length + 2) >> 1;
        if ( v19 )
        {
          Buffer = UnicodeString.Buffer;
          v21 = (unsigned __int64)UnicodeString.Length >> 1;
          do
          {
            if ( !v21 )
              break;
            if ( !*Buffer )
              break;
            *v18++ = *Buffer++;
            --v21;
            --v19;
          }
          while ( v19 );
          v22 = v18 - 1;
          if ( v19 )
            v22 = v18;
          *v22 = 0;
          v16 = -2147483643;
          if ( v19 )
          {
            RtlFreeUnicodeString(&UnicodeString);
            SetLastError(0);
            return v8;
          }
        }
        else
        {
          v16 = -1073741811;
        }
      }
      else
      {
        RtlFreeUnicodeString(&UnicodeString);
        v16 = -1073741801;
      }
    }
    v23 = RtlNtStatusToDosError(v16);
    SetLastError(v23);
    return GetLastError();
  }
  return 87;
}

```

## disassembly

```asm
0x180002fa0  mov     r11, rsp
0x180002fa3  mov     [r11+20h], rbx
0x180002fa7  push    rsi
0x180002fa8  sub     rsp, 50h
0x180002fac  mov     qword ptr [r11+8], 0
0x180002fb4  mov     rsi, rdx
0x180002fb7  mov     rbx, rcx
0x180002fba  test    rcx, rcx
0x180002fbd  jz      loc_180003143
0x180002fc3  test    rdx, rdx
0x180002fc6  jz      loc_180003143
0x180002fcc  lea     rax, [r11+8]
0x180002fd0  mov     [r11+10h], rbp
0x180002fd4  mov     [r11-28h], rax
0x180002fd8  mov     rdx, rcx; Sid
0x180002fdb  movzx   eax, [rsp+58h+arg_28]
0x180002fe3  xor     ecx, ecx; String1
0x180002fe5  mov     [rsp+58h+var_30], al; char
0x180002fe9  xor     ebp, ebp
0x180002feb  mov     rax, [rsp+58h+arg_20]
0x180002ff3  mov     [r11-38h], rax
0x180002ff7  mov     [r11+18h], rdi
0x180002ffb  call    LookupSidInTable
0x180003000  mov     rdi, rax
0x180003003  test    rax, rax
0x180003006  jz      short loc_180003062
0x180003008  mov     eax, [rax+0Ch]
0x18000300b  mov     ebx, eax
0x18000300d  mov     ecx, 40h ; '@'; uFlags
0x180003012  lea     rbx, ds:2[rbx*2]
0x18000301a  mov     rdx, rbx; uBytes
0x18000301d  call    cs:__imp_LocalAlloc
0x180003023  mov     [rsi], rax
0x180003026  test    rax, rax
0x180003029  jz      loc_180003170
0x18000302f  shr     rbx, 1
0x180003032  mov     rcx, rax; Destination
0x180003035  mov     rdx, rbx; SizeInWords
0x180003038  test    rdi, rdi
0x18000303b  jz      loc_18000317A
0x180003041  lea     r8, [rdi+2]; Source
0x180003045  call    cs:__imp_wcscpy_s
0x18000304b  mov     rdi, [rsp+58h+arg_10]
0x180003050  mov     eax, ebp
0x180003052  mov     rbp, [rsp+58h+arg_8]
0x180003057  mov     rbx, [rsp+58h+arg_18]
0x18000305c  add     rsp, 50h
0x180003060  pop     rsi
0x180003061  retn
0x180003062  cmp     [rsp+58h+arg_0], rbp
0x180003067  jnz     loc_180003166
0x18000306d  xorps   xmm0, xmm0
0x180003070  lea     rcx, [rsp+58h+UnicodeString]; UnicodeString
0x180003075  mov     r8b, 1; AllocateDestinationString
0x180003078  mov     rdx, rbx; Sid
0x18000307b  movups  xmmword ptr [rsp+58h+UnicodeString.Length], xmm0
0x180003080  call    cs:__imp_RtlConvertSidToUnicodeString
0x180003086  mov     ecx, eax
0x180003088  test    eax, eax
0x18000308a  js      loc_180003110
0x180003090  movzx   edx, [rsp+58h+UnicodeString.Length]
0x180003095  mov     ecx, 40h ; '@'; uFlags
0x18000309a  add     rdx, 2; uBytes
0x18000309e  call    cs:__imp_LocalAlloc
0x1800030a4  mov     [rsi], rax
0x1800030a7  mov     r8, rax
0x1800030aa  test    rax, rax
0x1800030ad  jz      loc_18000314D
0x1800030b3  movzx   eax, [rsp+58h+UnicodeString.Length]
0x1800030b8  lea     rdx, [rax+2]
0x1800030bc  shr     rdx, 1
0x1800030bf  jz      loc_18000315F
0x1800030c5  mov     r9, [rsp+58h+UnicodeString.Buffer]
0x1800030ca  shr     rax, 1
0x1800030cd  nop     dword ptr [rax]
0x1800030d0  test    rax, rax
0x1800030d3  jz      short loc_1800030F3
0x1800030d5  movzx   ecx, word ptr [r9]
0x1800030d9  test    cx, cx
0x1800030dc  jz      short loc_1800030F3
0x1800030de  mov     [r8], cx
0x1800030e2  add     r9, 2
0x1800030e6  add     r8, 2
0x1800030ea  dec     rax
0x1800030ed  sub     rdx, 1
0x1800030f1  jnz     short loc_1800030D0
0x1800030f3  test    rdx, rdx
0x1800030f6  lea     rcx, [r8-2]
0x1800030fa  cmovnz  rcx, r8
0x1800030fe  xor     eax, eax
0x180003100  test    rdx, rdx
0x180003103  mov     [rcx], ax
0x180003106  mov     ecx, 80000005h
0x18000310b  cmovnz  ecx, eax; Status
0x18000310e  jnz     short loc_18000312B
0x180003110  call    cs:__imp_RtlNtStatusToDosError
0x180003116  mov     ecx, eax; dwErrCode
0x180003118  call    cs:__imp_SetLastError
0x18000311e  call    cs:__imp_GetLastError
0x180003124  mov     ebp, eax
0x180003126  jmp     loc_18000304B
0x18000312b  lea     rcx, [rsp+58h+UnicodeString]; UnicodeString
0x180003130  call    cs:__imp_RtlFreeUnicodeString
0x180003136  xor     ecx, ecx; dwErrCode
0x180003138  call    cs:__imp_SetLastError
0x18000313e  jmp     loc_18000304B
0x180003143  mov     eax, 57h ; 'W'
0x180003148  jmp     loc_180003057
0x18000314d  lea     rcx, [rsp+58h+UnicodeString]; UnicodeString
0x180003152  call    cs:__imp_RtlFreeUnicodeString
0x180003158  mov     ecx, 0C0000017h
0x18000315d  jmp     short loc_180003110
0x18000315f  mov     ecx, 0C000000Dh
0x180003164  jmp     short loc_180003110
0x180003166  mov     eax, 2
0x18000316b  jmp     loc_18000300B
0x180003170  mov     ebp, 8
0x180003175  jmp     loc_18000304B
0x18000317a  lea     r8, aSa; "SA"
0x180003181  jmp     loc_180003045
```
