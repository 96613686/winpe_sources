# CContentEnum::_EnsureEnumThread(void)

- ea: `0x18001d1f4`
- end: `0x18001d32e`
- name: `?_EnsureEnumThread@CContentEnum@@AEAAJXZ`
- size: `314`
- prototype: `__int64 __fastcall(CContentEnum *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001cea0`

## callees

- `0x18000bde4`
- `0x18001d1f4`
- `0x18002d020`
- `0x18002ff5c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001d2eb`
- `KERNEL32!CloseHandle` at `0x18001d2eb`
- `KERNEL32!CreateEventW` at `0x18001d26b`
- `KERNEL32!CreateEventW` at `0x18001d26b`
- `SHLWAPI!__imp_SHCreateThread` at `0x18001d29f`
- `SHLWAPI!__imp_SHCreateThread` at `0x18001d29f`

## pseudocode

```c
__int64 __fastcall CContentEnum::_EnsureEnumThread(CContentEnum *this)
{
  char *v1; // rsi
  unsigned int v3; // ebx
  PVOID *v4; // rcx
  HANDLE EventW; // rax
  void *v6; // rcx

  v1 = (char *)this + 184;
  if ( *((_QWORD *)this + 23) )
    return 0;
  if ( (unsigned int)CDPA_Base<PROPERTY_ITEM>::Create((char *)this + 184) )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 6) = EventW;
    if ( EventW )
    {
      if ( SHCreateThread((LPTHREAD_START_ROUTINE)EnumThreadProc, this, 8u, EnumThread_AddRefCallBack) )
        return 0;
      v3 = -2147467259;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_dfacde6f4b3f3ae519c2a03af24374aa_Traceguids, 2147500037LL);
    }
    else
    {
      v3 = -2147467259;
    }
    CDPA<_ITEMIDLIST __unaligned>::DestroyCallback(v1);
    v6 = (void *)*((_QWORD *)this + 6);
    if ( v6 )
    {
      CloseHandle(v6);
      *((_QWORD *)this + 6) = 0;
    }
  }
  else
  {
    v3 = -2147024882;
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v3;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_16;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_dfacde6f4b3f3ae519c2a03af24374aa_Traceguids, 2147942414LL);
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
LABEL_16:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
    WPP_SF_d(v4[2], 17, WPP_dfacde6f4b3f3ae519c2a03af24374aa_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18001d1f4  push    rbx
0x18001d1f6  push    rbp
0x18001d1f7  push    rsi
0x18001d1f8  push    rdi
0x18001d1f9  sub     rsp, 28h
0x18001d1fd  lea     rsi, [rcx+0B8h]
0x18001d204  mov     rdi, rcx
0x18001d207  cmp     qword ptr [rsi], 0
0x18001d20b  jz      short loc_18001D214
0x18001d20d  xor     ebx, ebx
0x18001d20f  jmp     loc_18001D323
0x18001d214  mov     rcx, rsi
0x18001d217  call    ?Create@?$CDPA_Base@UPROPERTY_ITEM@@@@QEAAHH@Z; CDPA_Base<PROPERTY_ITEM>::Create(int)
0x18001d21c  test    eax, eax
0x18001d21e  jnz     short loc_18001D261
0x18001d220  mov     ebx, 8007000Eh
0x18001d225  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d22c  lea     rbp, WPP_GLOBAL_Control
0x18001d233  cmp     rcx, rbp
0x18001d236  jz      loc_18001D323
0x18001d23c  test    byte ptr [rcx+1Ch], 2
0x18001d240  jz      loc_18001D300
0x18001d246  mov     rcx, [rcx+10h]
0x18001d24a  lea     edx, [rax+0Fh]
0x18001d24d  mov     r9d, ebx
0x18001d250  lea     r8, WPP_dfacde6f4b3f3ae519c2a03af24374aa_Traceguids
0x18001d257  call    WPP_SF_d
0x18001d25c  jmp     loc_18001D2F9
0x18001d261  xor     r9d, r9d; lpName
0x18001d264  xor     r8d, r8d; bInitialState
0x18001d267  xor     edx, edx; bManualReset
0x18001d269  xor     ecx, ecx; lpEventAttributes
0x18001d26b  call    cs:__imp_CreateEventW
0x18001d271  mov     [rdi+30h], rax
0x18001d275  lea     rbp, WPP_GLOBAL_Control
0x18001d27c  test    rax, rax
0x18001d27f  jnz     short loc_18001D288
0x18001d281  mov     ebx, 80004005h
0x18001d286  jmp     short loc_18001D2DA
0x18001d288  lea     r9, ?EnumThread_AddRefCallBack@@YAKPEAX@Z; pfnCallback
0x18001d28f  mov     r8d, 8; flags
0x18001d295  mov     rdx, rdi; pData
0x18001d298  lea     rcx, ?EnumThreadProc@@YAKPEAX@Z; pfnThreadProc
0x18001d29f  call    cs:__imp_SHCreateThread
0x18001d2a5  test    eax, eax
0x18001d2a7  jnz     loc_18001D20D
0x18001d2ad  mov     ebx, 80004005h
0x18001d2b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d2b9  cmp     rcx, rbp
0x18001d2bc  jz      short loc_18001D2DA
0x18001d2be  test    byte ptr [rcx+1Ch], 2
0x18001d2c2  jz      short loc_18001D2DA
0x18001d2c4  mov     rcx, [rcx+10h]
0x18001d2c8  lea     edx, [rax+10h]
0x18001d2cb  mov     r9d, ebx
0x18001d2ce  lea     r8, WPP_dfacde6f4b3f3ae519c2a03af24374aa_Traceguids
0x18001d2d5  call    WPP_SF_d
0x18001d2da  mov     rcx, rsi
0x18001d2dd  call    ?DestroyCallback@?$CDPA@$$CFAU_ITEMIDLIST@@@@QEAAXP6AHPEFAU_ITEMIDLIST@@PEAX@Z1@Z; CDPA<_ITEMIDLIST>::DestroyCallback(int (*)(_ITEMIDLIST *,void *),void *)
0x18001d2e2  mov     rcx, [rdi+30h]; hObject
0x18001d2e6  test    rcx, rcx
0x18001d2e9  jz      short loc_18001D2F9
0x18001d2eb  call    cs:__imp_CloseHandle
0x18001d2f1  mov     qword ptr [rdi+30h], 0
0x18001d2f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d300  cmp     rcx, rbp
0x18001d303  jz      short loc_18001D323
0x18001d305  test    byte ptr [rcx+1Ch], 2
0x18001d309  jz      short loc_18001D323
0x18001d30b  mov     rcx, [rcx+10h]
0x18001d30f  lea     r8, WPP_dfacde6f4b3f3ae519c2a03af24374aa_Traceguids
0x18001d316  mov     edx, 11h
0x18001d31b  mov     r9d, ebx
0x18001d31e  call    WPP_SF_d
0x18001d323  mov     eax, ebx
0x18001d325  add     rsp, 28h
0x18001d329  pop     rdi
0x18001d32a  pop     rsi
0x18001d32b  pop     rbp
0x18001d32c  pop     rbx
0x18001d32d  retn
```
