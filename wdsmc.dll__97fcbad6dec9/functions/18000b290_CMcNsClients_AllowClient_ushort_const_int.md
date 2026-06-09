# CMcNsClients::AllowClient(ushort const *,int *)

- ea: `0x18000b290`
- end: `0x18000b39f`
- name: `?AllowClient@CMcNsClients@@QEAAKPEBGPEAH@Z`
- size: `271`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection, const unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180002c70`
- `0x18000b178`

## callees

- `0x18000b290`
- `0x18001a9a8`
- `0x180025450`
- `0x180025850`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000b32d`
- `msvcrt!_wcsicmp` at `0x18000b32d`
- `KERNEL32!LeaveCriticalSection` at `0x18000b388`
- `KERNEL32!LeaveCriticalSection` at `0x18000b388`
- `KERNEL32!EnterCriticalSection` at `0x18000b2ad`
- `KERNEL32!EnterCriticalSection` at `0x18000b2ad`

## string_xrefs

- `0x18000b2e3`: `onecore\base\eco\wds\wdslib\common\src\wdsidn.cpp`
- `0x18000b30c`: `onecore\base\eco\wds\wdslib\common\src\wdsidn.cpp`

## pseudocode

```c
__int64 __fastcall CMcNsClients::AllowClient(LPCRITICAL_SECTION lpCriticalSection, const char *a2, int *a3)
{
  int v3; // ebx
  unsigned int v5; // esi
  __int64 v7; // rcx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // r14
  const char *v9; // rdx
  int v10; // r12d
  wchar_t *v11; // rdi
  const char *v12; // rdx
  const char *v13; // rdx
  __int64 v14; // rcx
  const char *v15; // rdx
  unsigned int v16; // eax
  wchar_t *String1; // [rsp+60h] [rbp+8h] BYREF
  const char *v19; // [rsp+68h] [rbp+10h]
  wchar_t *String2; // [rsp+78h] [rbp+20h] BYREF

  v19 = a2;
  v3 = 0;
  v5 = 0;
  EnterCriticalSection(lpCriticalSection);
  DebugInfo = lpCriticalSection[1].DebugInfo;
  while ( DebugInfo )
  {
    v9 = (const char *)DebugInfo;
    String1 = 0;
    DebugInfo = *(PRTL_CRITICAL_SECTION_DEBUG *)&DebugInfo->EntryCount;
    v10 = 0;
    String2 = 0;
    v11 = 0;
    v5 = WdsIdnToAscii(v7, v9, &String1);
    if ( !ElValidateWin32(v5, v12, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdsidn.cpp", 0xD1u) )
    {
      v5 = WdsIdnToAscii(v14, v19, &String2);
      v16 = ElValidateWin32(v5, v15, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdsidn.cpp", 0xD6u);
      v11 = String2;
      if ( !v16 )
        v10 = _wcsicmp(String1, String2);
    }
    if ( String1 )
      operator delete(String1);
    if ( v11 )
      operator delete(v11);
    if ( ElValidateWin32(v5, v13, "base\\eco\\wds\\transport\\server\\mc\\mcnsclients.cpp", 0xA9u) )
      goto LABEL_15;
    if ( !v10 )
    {
      v3 = 1;
      break;
    }
  }
  *a3 = v3;
LABEL_15:
  LeaveCriticalSection(lpCriticalSection);
  return v5;
}

```

## disassembly

```asm
0x18000b290  mov     [rsp+arg_8], rdx
0x18000b295  push    rbx
0x18000b296  push    rbp
0x18000b297  push    rsi
0x18000b298  push    rdi
0x18000b299  push    r12
0x18000b29b  push    r13
0x18000b29d  push    r14
0x18000b29f  sub     rsp, 20h
0x18000b2a3  xor     ebx, ebx
0x18000b2a5  mov     r13, r8
0x18000b2a8  mov     esi, ebx
0x18000b2aa  mov     rbp, rcx
0x18000b2ad  call    cs:__imp_EnterCriticalSection
0x18000b2b3  mov     r14, [rbp+28h]
0x18000b2b7  jmp     loc_18000B371
0x18000b2bc  mov     rdx, r14
0x18000b2bf  mov     [rsp+58h+String1], rbx
0x18000b2c4  mov     r14, [r14+20h]
0x18000b2c8  lea     r8, [rsp+58h+String1]
0x18000b2cd  mov     r12d, ebx
0x18000b2d0  mov     [rsp+58h+String2], rbx
0x18000b2d5  mov     rdi, rbx
0x18000b2d8  call    WdsIdnToAscii
0x18000b2dd  mov     r9d, 0D1h; unsigned int
0x18000b2e3  lea     r8, aOnecoreBaseEco_1; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18000b2ea  mov     ecx, eax; unsigned int
0x18000b2ec  mov     esi, eax
0x18000b2ee  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000b2f3  test    eax, eax
0x18000b2f5  jnz     short loc_18000B336
0x18000b2f7  mov     rdx, [rsp+58h+arg_8]
0x18000b2fc  lea     r8, [rsp+58h+String2]
0x18000b301  call    WdsIdnToAscii
0x18000b306  mov     r9d, 0D6h; unsigned int
0x18000b30c  lea     r8, aOnecoreBaseEco_1; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18000b313  mov     ecx, eax; unsigned int
0x18000b315  mov     esi, eax
0x18000b317  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000b31c  mov     rdi, [rsp+58h+String2]
0x18000b321  test    eax, eax
0x18000b323  jnz     short loc_18000B336
0x18000b325  mov     rcx, [rsp+58h+String1]; String1
0x18000b32a  mov     rdx, rdi; String2
0x18000b32d  call    cs:__imp__wcsicmp
0x18000b333  mov     r12d, eax
0x18000b336  cmp     [rsp+58h+String1], rbx
0x18000b33b  jz      short loc_18000B347
0x18000b33d  mov     rcx, [rsp+58h+String1]; void *
0x18000b342  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b347  test    rdi, rdi
0x18000b34a  jz      short loc_18000B354
0x18000b34c  mov     rcx, rdi; void *
0x18000b34f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b354  mov     r9d, 0A9h; unsigned int
0x18000b35a  lea     r8, aBaseEcoWdsTran_19; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000b361  mov     ecx, esi; unsigned int
0x18000b363  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000b368  test    eax, eax
0x18000b36a  jnz     short loc_18000B385
0x18000b36c  test    r12d, r12d
0x18000b36f  jz      short loc_18000B37C
0x18000b371  test    r14, r14
0x18000b374  jnz     loc_18000B2BC
0x18000b37a  jmp     short loc_18000B381
0x18000b37c  mov     ebx, 1
0x18000b381  mov     [r13+0], ebx
0x18000b385  mov     rcx, rbp; lpCriticalSection
0x18000b388  call    cs:__imp_LeaveCriticalSection
0x18000b38e  mov     eax, esi
0x18000b390  add     rsp, 20h
0x18000b394  pop     r14
0x18000b396  pop     r13
0x18000b398  pop     r12
0x18000b39a  pop     rdi
0x18000b39b  pop     rsi
0x18000b39c  pop     rbp
0x18000b39d  pop     rbx
0x18000b39e  retn
```
