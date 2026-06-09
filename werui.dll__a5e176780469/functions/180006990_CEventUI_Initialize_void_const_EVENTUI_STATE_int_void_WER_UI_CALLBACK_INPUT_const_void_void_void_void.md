# CEventUI::Initialize(void * const,EVENTUI_STATE,int (*)(void *,_WER_UI_CALLBACK_INPUT * const),void *,void *,void *,void *)

- ea: `0x180006990`
- end: `0x180006b09`
- name: `?Initialize@CEventUI@@QEAAJQEAXW4EVENTUI_STATE@@P6AHPEAXQEAU_WER_UI_CALLBACK_INPUT@@@Z2222@Z`
- size: `377`
- prototype: `int __high(void *const, enum EVENTUI_STATE, int (__high *)(void *, struct _WER_UI_CALLBACK_INPUT *const), void *, void *, void *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800038e0`

## callees

- `0x1800035dc`
- `0x180003604`
- `0x180003fe4`
- `0x180006990`
- `0x18000983c`
- `0x18000c13c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180006a84`
- `KERNEL32!GetLastError` at `0x180006a84`
- `KERNEL32!CreateEventW` at `0x180006a67`
- `KERNEL32!CreateEventW` at `0x180006a67`

## pseudocode

```c
__int64 __fastcall CEventUI::Initialize(
        __int64 a1,
        void *a2,
        int a3,
        int (*a4)(void *, struct _WER_UI_CALLBACK_INPUT *const),
        void *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  int v10; // eax
  unsigned int v11; // ebx
  HANDLE EventW; // rax
  DWORD LastError; // eax

  if ( a2 && a6 && a7 && a8 )
  {
    v10 = CUIDlgBase::Initialize((CUIDlgBase *)(a1 + 8), a2, a4, a5);
    v11 = v10;
    if ( v10 >= 0 )
    {
      *(_DWORD *)(a1 + 176) = a3;
      *(_QWORD *)(a1 + 168) = a6;
      *(_QWORD *)(a1 + 200) = a7;
      *(_QWORD *)(a1 + 952) = a8;
      EventW = CreateEventW(0, 0, 0, 0);
      tlx::unique_any<tlx::file_handle_traits>::reset(a1 + 192, EventW);
      if ( *(_QWORD *)(a1 + 192) == -1 || *(_QWORD *)(a1 + 192) == 0 )
      {
        LastError = GetLastError();
        v11 = ERROR_HR_FROM_WIN32(LastError);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids);
      }
      else
      {
        return 0;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        &WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids,
        (unsigned int)v10);
    }
    return v11;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180006990  push    rbx
0x180006992  push    rbp
0x180006993  push    rsi
0x180006994  push    rdi
0x180006995  push    r14
0x180006997  push    r15
0x180006999  sub     rsp, 28h
0x18000699d  mov     rax, r9
0x1800069a0  mov     r15d, r8d
0x1800069a3  mov     rdi, rcx
0x1800069a6  test    rdx, rdx
0x1800069a9  jz      loc_180006AC9
0x1800069af  mov     rsi, [rsp+58h+arg_28]
0x1800069b7  test    rsi, rsi
0x1800069ba  jz      loc_180006AC9
0x1800069c0  mov     rbp, [rsp+58h+arg_30]
0x1800069c8  test    rbp, rbp
0x1800069cb  jz      loc_180006AC9
0x1800069d1  mov     r14, [rsp+58h+arg_38]
0x1800069d9  test    r14, r14
0x1800069dc  jz      loc_180006AC9
0x1800069e2  mov     r9, [rsp+58h+arg_20]; void *
0x1800069ea  add     rcx, 8; this
0x1800069ee  mov     r8, rax; int (*)(void *, struct _WER_UI_CALLBACK_INPUT *const)
0x1800069f1  call    ?Initialize@CUIDlgBase@@IEAAJPEAXP6AH0QEAU_WER_UI_CALLBACK_INPUT@@@Z0@Z; CUIDlgBase::Initialize(void *,int (*)(void *,_WER_UI_CALLBACK_INPUT * const),void *)
0x1800069f6  mov     ebx, eax
0x1800069f8  test    eax, eax
0x1800069fa  jns     short loc_180006A3A
0x1800069fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a03  lea     rdx, WPP_GLOBAL_Control
0x180006a0a  cmp     rcx, rdx
0x180006a0d  jz      loc_180006AC5
0x180006a13  test    byte ptr [rcx+1Ch], 1
0x180006a17  jz      loc_180006AC5
0x180006a1d  mov     rcx, [rcx+10h]
0x180006a21  lea     r8, WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids
0x180006a28  mov     edx, 0Bh
0x180006a2d  mov     r9d, eax
0x180006a30  call    WPP_SF_d
0x180006a35  jmp     loc_180006AC5
0x180006a3a  xor     r9d, r9d; lpName
0x180006a3d  mov     [rdi+0B0h], r15d
0x180006a44  xor     r8d, r8d; bInitialState
0x180006a47  mov     [rdi+0A8h], rsi
0x180006a4e  xor     edx, edx; bManualReset
0x180006a50  mov     [rdi+0C8h], rbp
0x180006a57  xor     ecx, ecx; lpEventAttributes
0x180006a59  mov     [rdi+3B8h], r14
0x180006a60  lea     rbx, [rdi+0C0h]
0x180006a67  call    cs:__imp_CreateEventW
0x180006a6d  mov     rdx, rax
0x180006a70  mov     rcx, rbx
0x180006a73  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180006a78  mov     rax, [rbx]
0x180006a7b  inc     rax
0x180006a7e  cmp     rax, 1
0x180006a82  ja      short loc_180006AC3
0x180006a84  call    cs:__imp_GetLastError
0x180006a8a  mov     ecx, eax; unsigned int
0x180006a8c  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180006a91  mov     ebx, eax
0x180006a93  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a9a  lea     rdx, WPP_GLOBAL_Control
0x180006aa1  cmp     rcx, rdx
0x180006aa4  jz      short loc_180006AC5
0x180006aa6  test    byte ptr [rcx+1Ch], 1
0x180006aaa  jz      short loc_180006AC5
0x180006aac  mov     rcx, [rcx+10h]
0x180006ab0  lea     r8, WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids
0x180006ab7  mov     edx, 0Ch
0x180006abc  call    WPP_SF_
0x180006ac1  jmp     short loc_180006AC5
0x180006ac3  xor     ebx, ebx
0x180006ac5  mov     eax, ebx
0x180006ac7  jmp     short loc_180006AFC
0x180006ac9  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ad0  lea     rdx, WPP_GLOBAL_Control
0x180006ad7  cmp     rcx, rdx
0x180006ada  jz      short loc_180006AF7
0x180006adc  test    byte ptr [rcx+1Ch], 1
0x180006ae0  jz      short loc_180006AF7
0x180006ae2  mov     rcx, [rcx+10h]
0x180006ae6  lea     r8, WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids
0x180006aed  mov     edx, 0Ah
0x180006af2  call    WPP_SF_
0x180006af7  mov     eax, 80070057h
0x180006afc  add     rsp, 28h
0x180006b00  pop     r15
0x180006b02  pop     r14
0x180006b04  pop     rdi
0x180006b05  pop     rsi
0x180006b06  pop     rbp
0x180006b07  pop     rbx
0x180006b08  retn
```
