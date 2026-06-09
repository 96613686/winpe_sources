# CAccountDisplayString::Initialize(wchar_t const *)

- ea: `0x180007768`
- end: `0x1800077e9`
- name: `?Initialize@CAccountDisplayString@@QEAAJPEB_W@Z`
- size: `129`
- prototype: `__int64 __fastcall(wchar_t **this, const wchar_t *)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180007d30`
- `0x180007de0`
- `0x180007e90`
- `0x180008510`
- `0x180008648`
- `0x1800087a8`

## callees

- `0x180003ab8`
- `0x180003be0`
- `0x180007768`
- `0x18000b4e8`
- `0x18000c444`

## pseudocode

```c
__int64 __fastcall CAccountDisplayString::Initialize(wchar_t **this, const wchar_t *a2, __int64 a3, void *a4)
{
  CAccountDisplayString *v7; // rcx
  __int64 v8; // r8
  void *v9; // r9
  int AccountNameFromSid; // edi
  void *v11; // rdx
  void *lpMem; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 )
    return ProfNotif_CreateStringCopy(&qword_180011360, this, a3, a4);
  lpMem = 0;
  if ( (int)ProfNotif_ConvertStringSidToSid(a2, &lpMem) < 0 )
    return (unsigned int)ProfNotif_CreateStringCopy(a2, this, v8, v9);
  AccountNameFromSid = CAccountDisplayString::_GetAccountNameFromSid(v7, lpMem, this);
  ProfNotif_HeapFree(lpMem, v11);
  if ( AccountNameFromSid < 0 )
    return (unsigned int)ProfNotif_CreateStringCopy(a2, this, v8, v9);
  return (unsigned int)AccountNameFromSid;
}

```

## disassembly

```asm
0x180007768  mov     [rsp+arg_0], rbx
0x18000776d  mov     [rsp+arg_10], rsi
0x180007772  push    rdi
0x180007773  sub     rsp, 20h
0x180007777  mov     rbx, rdx
0x18000777a  mov     rsi, rcx
0x18000777d  test    rdx, rdx
0x180007780  jnz     short loc_180007793
0x180007782  mov     rdx, rcx; wchar_t **
0x180007785  lea     rcx, qword_180011360; wchar_t *
0x18000778c  call    ?ProfNotif_CreateStringCopy@@YAJPEB_WPEAPEA_W@Z; ProfNotif_CreateStringCopy(wchar_t const *,wchar_t * *)
0x180007791  jmp     short loc_1800077D9
0x180007793  lea     rdx, [rsp+28h+lpMem]; void **
0x180007798  mov     [rsp+28h+lpMem], 0
0x1800077a1  mov     rcx, rbx; wchar_t *
0x1800077a4  call    ?ProfNotif_ConvertStringSidToSid@@YAJPEB_WPEAPEAX@Z; ProfNotif_ConvertStringSidToSid(wchar_t const *,void * *)
0x1800077a9  test    eax, eax
0x1800077ab  js      short loc_1800077CA
0x1800077ad  mov     rdx, [rsp+28h+lpMem]; void *
0x1800077b2  mov     r8, rsi; wchar_t **
0x1800077b5  call    ?_GetAccountNameFromSid@CAccountDisplayString@@AEAAJPEAXPEAPEA_W@Z; CAccountDisplayString::_GetAccountNameFromSid(void *,wchar_t * *)
0x1800077ba  mov     rcx, [rsp+28h+lpMem]; lpMem
0x1800077bf  mov     edi, eax
0x1800077c1  call    ?ProfNotif_HeapFree@@YAJPEAX0@Z; ProfNotif_HeapFree(void *,void *)
0x1800077c6  test    edi, edi
0x1800077c8  jns     short loc_1800077D7
0x1800077ca  mov     rdx, rsi; wchar_t **
0x1800077cd  mov     rcx, rbx; wchar_t *
0x1800077d0  call    ?ProfNotif_CreateStringCopy@@YAJPEB_WPEAPEA_W@Z; ProfNotif_CreateStringCopy(wchar_t const *,wchar_t * *)
0x1800077d5  mov     edi, eax
0x1800077d7  mov     eax, edi
0x1800077d9  mov     rbx, [rsp+28h+arg_0]
0x1800077de  mov     rsi, [rsp+28h+arg_10]
0x1800077e3  add     rsp, 20h
0x1800077e7  pop     rdi
0x1800077e8  retn
```
