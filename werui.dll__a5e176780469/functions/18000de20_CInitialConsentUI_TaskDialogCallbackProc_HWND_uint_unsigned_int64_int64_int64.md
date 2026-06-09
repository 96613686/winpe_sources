# CInitialConsentUI::TaskDialogCallbackProc(HWND__ *,uint,unsigned __int64,__int64,__int64)

- ea: `0x18000de20`
- end: `0x18000df10`
- name: `?TaskDialogCallbackProc@CInitialConsentUI@@AEAAJPEAUHWND__@@I_K_J2@Z`
- size: `240`
- prototype: `__int64 __fastcall(CInitialConsentUI *__hidden this, HWND, unsigned int, unsigned __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000ddd0`

## callees

- `0x18000c8a0`
- `0x18000cb5c`
- `0x18000d114`
- `0x18000d428`
- `0x18000de20`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18000de93`
- `KERNEL32!SetEvent` at `0x18000def1`
- `KERNEL32!SetEvent` at `0x18000de93`
- `KERNEL32!SetEvent` at `0x18000def1`

## pseudocode

```c
__int64 __fastcall CInitialConsentUI::TaskDialogCallbackProc(HANDLE *this, HWND a2, int a3, __int64 a4)
{
  unsigned int v4; // esi

  v4 = 0;
  if ( a3 )
  {
    if ( a3 == 2 )
    {
      CUIDlgBase::UICallback(this, 8);
      if ( a4 == 8 )
      {
        CInitialConsentUI::HandleCancellation((CInitialConsentUI *)this);
        return 1;
      }
      else
      {
        *((_DWORD *)this + 92) = a4;
        if ( (((_DWORD)a4 - 2) & 0xFFFFFFFC) != 0 || (_DWORD)a4 == 4 )
          v4 = 1;
        SetEvent(this[45]);
      }
    }
    else if ( a3 == 4 )
    {
      CInitialConsentUI::OnTimer((CInitialConsentUI *)this, a2);
    }
    else if ( a3 == 10 && a4 )
    {
      if ( !*((_DWORD *)this + 85) && !*((_DWORD *)this + 84) )
      {
        *((_DWORD *)this + 85) = 1;
        if ( !(unsigned int)CUIDlgBase::UICallback(this, 4) )
          SetEvent(this[40]);
      }
      CUIDlgBase::UICallback(this, 13);
    }
  }
  else
  {
    CInitialConsentUI::OnCreated((DWORD_PTR)this, a2);
  }
  return v4;
}

```

## disassembly

```asm
0x18000de20  mov     [rsp+arg_0], rbx
0x18000de25  mov     [rsp+arg_8], rsi
0x18000de2a  push    rdi
0x18000de2b  sub     rsp, 20h
0x18000de2f  xor     esi, esi
0x18000de31  mov     rdi, r9
0x18000de34  mov     rbx, rcx
0x18000de37  test    r8d, r8d
0x18000de3a  jz      loc_18000DEF9
0x18000de40  cmp     r8d, 2
0x18000de44  jz      short loc_18000DEB1
0x18000de46  cmp     r8d, 4
0x18000de4a  jz      short loc_18000DEAA
0x18000de4c  cmp     r8d, 0Ah
0x18000de50  jnz     loc_18000DEFE
0x18000de56  test    r9, r9
0x18000de59  jz      loc_18000DEFE
0x18000de5f  cmp     [rcx+154h], esi
0x18000de65  jnz     short loc_18000DE99
0x18000de67  cmp     [rcx+150h], esi
0x18000de6d  jnz     short loc_18000DE99
0x18000de6f  mov     r8, [rcx+140h]
0x18000de76  lea     edx, [rsi+4]
0x18000de79  mov     dword ptr [rcx+154h], 1
0x18000de83  call    ?UICallback@CUIDlgBase@@IEAAHW4_UICALLBACKTYPE@@_K@Z; CUIDlgBase::UICallback(_UICALLBACKTYPE,unsigned __int64)
0x18000de88  test    eax, eax
0x18000de8a  jnz     short loc_18000DE99
0x18000de8c  mov     rcx, [rbx+140h]; hEvent
0x18000de93  call    cs:__imp_SetEvent
0x18000de99  xor     r8d, r8d
0x18000de9c  mov     rcx, rbx
0x18000de9f  lea     edx, [r8+0Dh]
0x18000dea3  call    ?UICallback@CUIDlgBase@@IEAAHW4_UICALLBACKTYPE@@_K@Z; CUIDlgBase::UICallback(_UICALLBACKTYPE,unsigned __int64)
0x18000dea8  jmp     short loc_18000DEFE
0x18000deaa  call    ?OnTimer@CInitialConsentUI@@AEAAJPEAUHWND__@@@Z; CInitialConsentUI::OnTimer(HWND__ *)
0x18000deaf  jmp     short loc_18000DEFE
0x18000deb1  xor     r8d, r8d
0x18000deb4  lea     edx, [r8+8]
0x18000deb8  call    ?UICallback@CUIDlgBase@@IEAAHW4_UICALLBACKTYPE@@_K@Z; CUIDlgBase::UICallback(_UICALLBACKTYPE,unsigned __int64)
0x18000debd  cmp     rdi, 8
0x18000dec1  jnz     short loc_18000DED0
0x18000dec3  mov     rcx, rbx; this
0x18000dec6  call    ?HandleCancellation@CInitialConsentUI@@AEAAHXZ; CInitialConsentUI::HandleCancellation(void)
0x18000decb  lea     esi, [rdi-7]
0x18000dece  jmp     short loc_18000DEFE
0x18000ded0  lea     eax, [rdi-2]
0x18000ded3  mov     [rbx+170h], edi
0x18000ded9  test    eax, 0FFFFFFFCh
0x18000dede  jnz     short loc_18000DEE5
0x18000dee0  cmp     edi, 4
0x18000dee3  jnz     short loc_18000DEEA
0x18000dee5  mov     esi, 1
0x18000deea  mov     rcx, [rbx+168h]; hEvent
0x18000def1  call    cs:__imp_SetEvent
0x18000def7  jmp     short loc_18000DEFE
0x18000def9  call    ?OnCreated@CInitialConsentUI@@AEAAJPEAUHWND__@@@Z; CInitialConsentUI::OnCreated(HWND__ *)
0x18000defe  mov     rbx, [rsp+28h+arg_0]
0x18000df03  mov     eax, esi
0x18000df05  mov     rsi, [rsp+28h+arg_8]
0x18000df0a  add     rsp, 20h
0x18000df0e  pop     rdi
0x18000df0f  retn
```
