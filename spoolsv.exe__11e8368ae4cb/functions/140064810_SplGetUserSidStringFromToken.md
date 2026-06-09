# SplGetUserSidStringFromToken

- ea: `0x140064810`
- end: `0x1400648ec`
- name: `SplGetUserSidStringFromToken`
- size: `220`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14000eb40`
- `0x14005d7b0`

## callees

- `0x1400140cc`
- `0x1400154c4`
- `0x14006372c`
- `0x140064810`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140064885`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140064885`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006485a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006485a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140064873`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140064873`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140064850`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140064850`

## string_xrefs

- `0x140064899`: `SplGetUserSidStringFromToken`

## pseudocode

```c
__int64 __fastcall SplGetUserSidStringFromToken(void *a1, unsigned __int16 *a2, unsigned int a3, unsigned int *a4)
{
  unsigned __int64 v5; // rsi
  DWORD TokenUserFromToken; // eax
  void *v8; // rdi
  DWORD LastError; // ebx
  unsigned __int16 *v10; // rcx
  __int64 v12; // rax
  unsigned int v13; // eax
  LPWSTR StringSid; // [rsp+20h] [rbp-48h] BYREF
  LPVOID lpMem; // [rsp+28h] [rbp-40h] BYREF

  v5 = a3;
  lpMem = 0;
  StringSid = 0;
  TokenUserFromToken = GetTokenUserFromToken(a1, (struct _TOKEN_USER **)&lpMem);
  v8 = lpMem;
  LastError = TokenUserFromToken;
  if ( TokenUserFromToken )
    goto LABEL_5;
  if ( !ConvertSidToStringSidW(*(PSID *)lpMem, &StringSid) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 8;
    goto LABEL_5;
  }
  v10 = StringSid;
  v12 = -1;
  do
    ++v12;
  while ( StringSid[v12] );
  v13 = 2 * v12 + 2;
  *a4 = v13;
  if ( v13 <= (unsigned int)v5 )
  {
    StringCbCopyW(a2, v5, v10);
LABEL_5:
    v10 = StringSid;
    goto LABEL_6;
  }
  LastError = 122;
LABEL_6:
  if ( v10 )
    LocalFree(v10);
  HeapFree(g_hSpoolssHeap, 0, v8);
  if ( LastError )
    PrvSpoolssTelemetry::WriteDbgTraceError("SplGetUserSidStringFromToken", L"Failed.  Error %d.", LastError);
  return LastError;
}

```

## disassembly

```asm
0x140064810  push    rbx
0x140064812  push    rbp
0x140064813  push    rsi
0x140064814  push    rdi
0x140064815  push    r14
0x140064817  push    r15
0x140064819  sub     rsp, 38h
0x14006481d  mov     rbp, rdx
0x140064820  mov     esi, r8d
0x140064823  xor     r15d, r15d
0x140064826  lea     rdx, [rsp+68h+lpMem]; struct _TOKEN_USER **
0x14006482b  mov     [rsp+68h+lpMem], r15
0x140064830  mov     r14, r9
0x140064833  mov     [rsp+68h+StringSid], r15
0x140064838  call    ?GetTokenUserFromToken@@YAKPEAXPEAPEAU_TOKEN_USER@@@Z; GetTokenUserFromToken(void *,_TOKEN_USER * *)
0x14006483d  mov     rdi, [rsp+68h+lpMem]
0x140064842  mov     ebx, eax
0x140064844  test    eax, eax
0x140064846  jnz     short loc_140064869
0x140064848  mov     rcx, [rdi]; Sid
0x14006484b  lea     rdx, [rsp+68h+StringSid]; StringSid
0x140064850  call    cs:__imp_ConvertSidToStringSidW
0x140064856  test    eax, eax
0x140064858  jnz     short loc_1400648B4
0x14006485a  call    cs:__imp_GetLastError
0x140064860  mov     ebx, eax
0x140064862  test    eax, eax
0x140064864  jnz     short loc_140064869
0x140064866  lea     ebx, [rax+8]
0x140064869  mov     rcx, [rsp+68h+StringSid]; hMem
0x14006486e  test    rcx, rcx
0x140064871  jz      short loc_140064879
0x140064873  call    cs:__imp_LocalFree
0x140064879  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140064880  mov     r8, rdi; lpMem
0x140064883  xor     edx, edx; dwFlags
0x140064885  call    cs:__imp_HeapFree
0x14006488b  test    ebx, ebx
0x14006488d  jz      short loc_1400648A5
0x14006488f  mov     r8d, ebx
0x140064892  lea     rdx, aFailedErrorD; "Failed.  Error %d."
0x140064899  lea     rcx, aSplgetusersids; "SplGetUserSidStringFromToken"
0x1400648a0  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400648a5  mov     eax, ebx
0x1400648a7  add     rsp, 38h
0x1400648ab  pop     r15
0x1400648ad  pop     r14
0x1400648af  pop     rdi
0x1400648b0  pop     rsi
0x1400648b1  pop     rbp
0x1400648b2  pop     rbx
0x1400648b3  retn
0x1400648b4  mov     rcx, [rsp+68h+StringSid]
0x1400648b9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400648bd  inc     rax
0x1400648c0  cmp     [rcx+rax*2], r15w
0x1400648c5  jnz     short loc_1400648BD
0x1400648c7  lea     eax, ds:2[rax*2]
0x1400648ce  mov     [r14], eax
0x1400648d1  cmp     eax, esi
0x1400648d3  ja      short loc_1400648E5
0x1400648d5  mov     r8, rcx; unsigned __int16 *
0x1400648d8  mov     rdx, rsi; unsigned __int64
0x1400648db  mov     rcx, rbp; unsigned __int16 *
0x1400648de  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1400648e3  jmp     short loc_140064869
0x1400648e5  mov     ebx, 7Ah ; 'z'
0x1400648ea  jmp     short loc_14006486E
```
