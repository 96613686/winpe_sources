# CEventUI::Start(void)

- ea: `0x180007a70`
- end: `0x180007baa`
- name: `?Start@CEventUI@@UEAA?AW4USER_SELECTION@@XZ`
- size: `314`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1800035dc`
- `0x180003604`
- `0x180006550`
- `0x18000765c`
- `0x180007a70`
- `0x180008fb8`
- `0x18000983c`
- `0x180009944`
- `0x180009ab8`

## import_xrefs

- `KERNEL32!CreateThread` at `0x180007ae7`
- `KERNEL32!CreateThread` at `0x180007ae7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CEventUI::Start(__int64 a1)
{
  unsigned int InitialDialogSelection; // eax
  unsigned int v3; // edi
  HANDLE v4; // rax
  int v5; // r9d
  void *v6; // rcx
  unsigned int v7; // eax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-1A8h]
  void *v10[2]; // [rsp+30h] [rbp-198h] BYREF
  _BYTE v11[392]; // [rsp+40h] [rbp-188h] BYREF
  DWORD ThreadId; // [rsp+1D8h] [rbp+10h] BYREF

  ThreadId = 0;
  CConsentUI::CConsentUI((CConsentUI *)v11);
  CEventUI::SetDefaultUIOptions((CEventUI *)a1);
  InitialDialogSelection = CEventUI::GetInitialDialogSelection(a1);
  v3 = InitialDialogSelection;
  if ( ((InitialDialogSelection - 2) & 0xFFFFFFFC) != 0 || InitialDialogSelection == 4 )
  {
    v4 = CreateThread(0, 0, CEventUI::UIThread_Static, (LPVOID)a1, 0, &ThreadId);
    tlx::unique_any<tlx::file_handle_traits>::reset(a1 + 144, v4);
    v6 = *(void **)(a1 + 144);
    if ( (unsigned __int64)v6 + 1 > 1 )
    {
      v10[0] = *(void **)(a1 + 192);
      v10[1] = v6;
      v7 = UtilMsgWaitForMultipleObjects((const unsigned __int16 *)v6, 2u, v10, v5, dwCreationFlags);
      if ( v7 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids, v7);
      }
      else if ( v3 == 11 )
      {
        v3 = 4;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids);
    }
  }
  CConsentUI::~CConsentUI((CConsentUI *)v11);
  return v3;
}

```

## disassembly

```asm
0x180007a70  mov     rax, rsp
0x180007a73  push    rbx
0x180007a74  push    rbp
0x180007a75  push    rsi
0x180007a76  push    rdi
0x180007a77  sub     rsp, 1A8h
0x180007a7e  mov     rsi, rcx
0x180007a81  mov     dword ptr [rax+10h], 0
0x180007a88  lea     rcx, [rsp+1C8h+var_188]; this
0x180007a8d  call    ??0CConsentUI@@QEAA@XZ; CConsentUI::CConsentUI(void)
0x180007a92  nop
0x180007a93  mov     rcx, rsi; this
0x180007a96  call    ?SetDefaultUIOptions@CEventUI@@AEAAJXZ; CEventUI::SetDefaultUIOptions(void)
0x180007a9b  mov     rcx, rsi
0x180007a9e  call    ?GetInitialDialogSelection@CEventUI@@AEAA?AW4USER_SELECTION@@XZ; CEventUI::GetInitialDialogSelection(void)
0x180007aa3  mov     edi, eax
0x180007aa5  lea     edx, [rax-2]
0x180007aa8  mov     ebp, 4
0x180007aad  test    edx, 0FFFFFFFCh
0x180007ab3  jnz     short loc_180007ABD
0x180007ab5  cmp     eax, ebp
0x180007ab7  jnz     loc_180007B92
0x180007abd  lea     rbx, [rsi+90h]
0x180007ac4  lea     rax, [rsp+1C8h+ThreadId]
0x180007acc  mov     [rsp+1C8h+lpThreadId], rax; lpThreadId
0x180007ad1  mov     [rsp+1C8h+dwCreationFlags], 0; unsigned int
0x180007ad9  mov     r9, rsi; lpParameter
0x180007adc  lea     r8, ?UIThread_Static@CEventUI@@CAKPEAX@Z; lpStartAddress
0x180007ae3  xor     edx, edx; dwStackSize
0x180007ae5  xor     ecx, ecx; lpThreadAttributes
0x180007ae7  call    cs:__imp_CreateThread
0x180007aed  mov     rdx, rax
0x180007af0  mov     rcx, rbx
0x180007af3  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180007af8  mov     rcx, [rbx]; unsigned __int16 *
0x180007afb  lea     rax, [rcx+1]
0x180007aff  cmp     rax, 1
0x180007b03  ja      short loc_180007B35
0x180007b05  lea     rax, WPP_GLOBAL_Control
0x180007b0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b13  cmp     rcx, rax
0x180007b16  jz      short loc_180007B92
0x180007b18  test    byte ptr [rcx+1Ch], 1
0x180007b1c  jz      short loc_180007B92
0x180007b1e  mov     edx, 16h
0x180007b23  lea     r8, WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids
0x180007b2a  mov     rcx, [rcx+10h]
0x180007b2e  call    WPP_SF_
0x180007b33  jmp     short loc_180007B92
0x180007b35  mov     rax, [rsi+0C0h]
0x180007b3c  mov     [rsp+1C8h+var_198], rax
0x180007b41  mov     [rsp+1C8h+var_190], rcx
0x180007b46  lea     r8, [rsp+1C8h+var_198]; void **
0x180007b4b  mov     edx, 2; unsigned int
0x180007b50  call    ?UtilMsgWaitForMultipleObjects@@YAKPEBGKQEAPEAXHK@Z; UtilMsgWaitForMultipleObjects(ushort const *,ulong,void * * const,int,ulong)
0x180007b55  mov     r9d, eax
0x180007b58  test    eax, eax
0x180007b5a  jz      short loc_180007B8C
0x180007b5c  lea     rax, WPP_GLOBAL_Control
0x180007b63  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b6a  cmp     rcx, rax
0x180007b6d  jz      short loc_180007B92
0x180007b6f  test    byte ptr [rcx+1Ch], 1
0x180007b73  jz      short loc_180007B92
0x180007b75  mov     edx, 17h
0x180007b7a  lea     r8, WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids
0x180007b81  mov     rcx, [rcx+10h]
0x180007b85  call    WPP_SF_d
0x180007b8a  jmp     short loc_180007B92
0x180007b8c  cmp     edi, 0Bh
0x180007b8f  cmovz   edi, ebp
0x180007b92  lea     rcx, [rsp+1C8h+var_188]; this
0x180007b97  call    ??1CConsentUI@@QEAA@XZ; CConsentUI::~CConsentUI(void)
0x180007b9c  mov     eax, edi
0x180007b9e  add     rsp, 1A8h
0x180007ba5  pop     rdi
0x180007ba6  pop     rsi
0x180007ba7  pop     rbp
0x180007ba8  pop     rbx
0x180007ba9  retn
```
