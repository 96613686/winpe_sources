# GetErrorMessage

- ea: `0x18002abe0`
- end: `0x18002adfd`
- name: `GetErrorMessage`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002c04c`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x18001e2c0`
- `0x180020228`
- `0x180022e80`
- `0x18002abe0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ac28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ac28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ac76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002acd1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ac76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002acd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ac03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ac03`

## string_xrefs

- `0x18002acfe`: `GetErrorMessage could not find ThreadEntry for connection 0x%x, thread 0x%x.  Creating one.\n`
- `0x18002ade6`: `GetErrorMessage no per-thread entry, connection 0x%x, thread 0x%x.\n`
- `0x18002adae`: `GetErrorMessage AddPerThreadEntry failed, connection 0x%x, thread 0x%x.\n`

## pseudocode

```c
__int64 __fastcall GetErrorMessage(__int64 a1, char a2)
{
  __int64 v2; // rsi
  char v5; // r14
  DWORD CurrentThreadId; // ebp
  __int64 v7; // rax
  __int64 v8; // rbx
  _QWORD *i; // rbx
  __int64 v11; // rdx
  void *v12; // rcx
  unsigned int v13; // eax

  v2 = 0;
  v5 = 0;
  CurrentThreadId = GetCurrentThreadId();
  while ( 1 )
  {
    EnterCriticalSection(&PerThreadListLock);
    v7 = GlobalPerThreadList;
    if ( (__int64 *)GlobalPerThreadList != &GlobalPerThreadList )
    {
      do
      {
        v8 = v7;
        if ( *(_DWORD *)(v7 + 16) == CurrentThreadId )
          break;
        v7 = *(_QWORD *)v7;
        v8 = 0;
      }
      while ( (__int64 *)v7 != &GlobalPerThreadList );
      if ( v8 )
        break;
    }
    LeaveCriticalSection(&PerThreadListLock);
    if ( v5 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(
          0x400000,
          "GetErrorMessage no per-thread entry, connection 0x%x, thread 0x%x.\n",
          a1,
          CurrentThreadId);
      v11 = 82;
      goto LABEL_12;
    }
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
      LDAPClientPrint(
        0x400000,
        "GetErrorMessage could not find ThreadEntry for connection 0x%x, thread 0x%x.  Creating one.\n",
        a1,
        CurrentThreadId);
    if ( !(unsigned int)AddPerThreadEntry(CurrentThreadId) )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(
          0x400000,
          "GetErrorMessage AddPerThreadEntry failed, connection 0x%x, thread 0x%x.\n",
          a1,
          CurrentThreadId);
      v11 = 90;
LABEL_12:
      SetConnectionError(a1, v11);
      return 0;
    }
    v5 = 1;
  }
  for ( i = *(_QWORD **)(v8 + 24); i && i[1] != a1; i = (_QWORD *)*i )
    ;
  LeaveCriticalSection(&PerThreadListLock);
  if ( i )
  {
    v12 = (void *)i[3];
    if ( v12 )
    {
      if ( a2 )
      {
        v2 = ldap_dup_stringW(v12);
        if ( !v2 )
          SetConnectionError(a1, 90);
      }
      else
      {
        v13 = FromUnicodeWithAlloc((LPCWCH)v12);
        if ( v13 )
          SetConnectionError(a1, v13);
        return 0;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18002abe0  mov     [rsp+arg_0], rbx
0x18002abe5  mov     [rsp+arg_8], rbp
0x18002abea  push    rsi
0x18002abeb  push    rdi
0x18002abec  push    r13
0x18002abee  push    r14
0x18002abf0  push    r15
0x18002abf2  sub     rsp, 20h
0x18002abf6  xor     esi, esi
0x18002abf8  mov     r15b, dl
0x18002abfb  mov     [rsp+48h+arg_10], rsi
0x18002ac00  mov     rdi, rcx
0x18002ac03  call    cs:__imp_GetCurrentThreadId
0x18002ac0a  nop     dword ptr [rax+rax+00h]
0x18002ac0f  xor     r14b, r14b
0x18002ac12  lea     rbx, GlobalPerThreadList
0x18002ac19  mov     ebp, eax
0x18002ac1b  mov     r13d, 400000h
0x18002ac21  lea     rcx, PerThreadListLock; lpCriticalSection
0x18002ac28  call    cs:__imp_EnterCriticalSection
0x18002ac2f  nop     dword ptr [rax+rax+00h]
0x18002ac34  mov     rax, cs:GlobalPerThreadList
0x18002ac3b  cmp     rax, rbx
0x18002ac3e  jz      loc_18002ACCA
0x18002ac44  lea     rcx, GlobalPerThreadList
0x18002ac4b  mov     rbx, rax
0x18002ac4e  cmp     [rax+10h], ebp
0x18002ac51  jz      short loc_18002AC5D
0x18002ac53  mov     rax, [rax]
0x18002ac56  xor     ebx, ebx
0x18002ac58  cmp     rax, rcx
0x18002ac5b  jnz     short loc_18002AC4B
0x18002ac5d  test    rbx, rbx
0x18002ac60  jz      short loc_18002ACC3
0x18002ac62  mov     rbx, [rbx+18h]
0x18002ac66  test    rbx, rbx
0x18002ac69  jnz     loc_18002AD23
0x18002ac6f  lea     rcx, PerThreadListLock; lpCriticalSection
0x18002ac76  call    cs:__imp_LeaveCriticalSection
0x18002ac7d  nop     dword ptr [rax+rax+00h]
0x18002ac82  test    rbx, rbx
0x18002ac85  jnz     loc_18002AD35
0x18002ac8b  mov     rax, rsi
0x18002ac8e  mov     rbx, [rsp+48h+arg_0]
0x18002ac93  mov     rbp, [rsp+48h+arg_8]
0x18002ac98  add     rsp, 20h
0x18002ac9c  pop     r15
0x18002ac9e  pop     r14
0x18002aca0  pop     r13
0x18002aca2  pop     rdi
0x18002aca3  pop     rsi
0x18002aca4  retn
0x18002aca6  cmp     cs:g_fTracingOn, esi
0x18002acac  jnz     loc_18002ADCA
0x18002acb2  mov     edx, 52h ; 'R'
0x18002acb7  mov     rcx, rdi
0x18002acba  call    SetConnectionError
0x18002acbf  xor     eax, eax
0x18002acc1  jmp     short loc_18002AC8E
0x18002acc3  lea     rbx, GlobalPerThreadList
0x18002acca  lea     rcx, PerThreadListLock; lpCriticalSection
0x18002acd1  call    cs:__imp_LeaveCriticalSection
0x18002acd8  nop     dword ptr [rax+rax+00h]
0x18002acdd  test    r14b, r14b
0x18002ace0  jnz     short loc_18002ACA6
0x18002ace2  cmp     cs:g_fTracingOn, esi
0x18002ace8  jz      short loc_18002AD10
0x18002acea  cmp     cs:g_fProviderEnabled, esi
0x18002acf0  jz      short loc_18002AD10
0x18002acf2  test    cs:g_ulTraceFlags, r13
0x18002acf9  jz      short loc_18002AD10
0x18002acfb  mov     r9d, ebp
0x18002acfe  lea     rdx, aGeterrormessag; "GetErrorMessage could not find ThreadEn"...
0x18002ad05  mov     r8, rdi
0x18002ad08  mov     ecx, r13d
0x18002ad0b  call    LDAPClientPrint
0x18002ad10  mov     ecx, ebp
0x18002ad12  call    AddPerThreadEntry
0x18002ad17  test    eax, eax
0x18002ad19  jz      short loc_18002AD92
0x18002ad1b  mov     r14b, 1
0x18002ad1e  jmp     loc_18002AC21
0x18002ad23  cmp     [rbx+8], rdi
0x18002ad27  jz      loc_18002AC6F
0x18002ad2d  mov     rbx, [rbx]
0x18002ad30  jmp     loc_18002AC66
0x18002ad35  mov     rcx, [rbx+18h]; lpWideCharStr
0x18002ad39  test    rcx, rcx
0x18002ad3c  jz      loc_18002AC8B
0x18002ad42  mov     r8d, 7272454Ch
0x18002ad48  test    r15b, r15b
0x18002ad4b  jz      short loc_18002AD70
0x18002ad4d  xor     edx, edx
0x18002ad4f  call    ldap_dup_stringW
0x18002ad54  mov     rsi, rax
0x18002ad57  test    rax, rax
0x18002ad5a  jnz     loc_18002AC8B
0x18002ad60  lea     edx, [rax+5Ah]
0x18002ad63  mov     rcx, rdi
0x18002ad66  call    SetConnectionError
0x18002ad6b  jmp     loc_18002AC8B
0x18002ad70  lea     rdx, [rsp+48h+arg_10]
0x18002ad75  call    FromUnicodeWithAlloc
0x18002ad7a  test    eax, eax
0x18002ad7c  jz      short loc_18002AD88
0x18002ad7e  mov     edx, eax
0x18002ad80  mov     rcx, rdi
0x18002ad83  call    SetConnectionError
0x18002ad88  mov     rsi, [rsp+48h+arg_10]
0x18002ad8d  jmp     loc_18002AC8B
0x18002ad92  cmp     cs:g_fTracingOn, esi
0x18002ad98  jz      short loc_18002ADC0
0x18002ad9a  cmp     cs:g_fProviderEnabled, esi
0x18002ada0  jz      short loc_18002ADC0
0x18002ada2  test    cs:g_ulTraceFlags, r13
0x18002ada9  jz      short loc_18002ADC0
0x18002adab  mov     r9d, ebp
0x18002adae  lea     rdx, aGeterrormessag_0; "GetErrorMessage AddPerThreadEntry faile"...
0x18002adb5  mov     r8, rdi
0x18002adb8  mov     ecx, r13d
0x18002adbb  call    LDAPClientPrint
0x18002adc0  mov     edx, 5Ah ; 'Z'
0x18002adc5  jmp     loc_18002ACB7
0x18002adca  cmp     cs:g_fProviderEnabled, esi
0x18002add0  jz      loc_18002ACB2
0x18002add6  test    cs:g_ulTraceFlags, r13
0x18002addd  jz      loc_18002ACB2
0x18002ade3  mov     r9d, ebp
0x18002ade6  lea     rdx, aGeterrormessag_1; "GetErrorMessage no per-thread entry, co"...
0x18002aded  mov     r8, rdi
0x18002adf0  mov     ecx, r13d
0x18002adf3  call    LDAPClientPrint
0x18002adf8  jmp     loc_18002ACB2
```
