# SqospDispatchDeferredJob

- ea: `0x140006a38`
- end: `0x140006afc`
- name: `SqospDispatchDeferredJob`
- size: `196`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140001940`

## callees

- `0x140001ab0`
- `0x14000666c`
- `0x140006a38`
- `0x140006b04`

## import_xrefs

- `FLTMGR!FltLockUserBuffer` at `0x140006a69`
- `FLTMGR!FltLockUserBuffer` at `0x140006a69`
- `FLTMGR!FltCompletePendedPreOperation` at `0x140006adf`
- `FLTMGR!FltCompletePendedPreOperation` at `0x140006adf`

## pseudocode

```c
void __fastcall SqospDispatchDeferredJob(LARGE_INTEGER *Entry)
{
  struct _FLT_CALLBACK_DATA *QuadPart; // rdi
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  int v4; // esi
  LARGE_INTEGER *v5; // r8
  FLT_PREOP_CALLBACK_STATUS v6; // edx

  QuadPart = (struct _FLT_CALLBACK_DATA *)Entry->QuadPart;
  if ( (*(_DWORD *)Entry->QuadPart & 8) != 0
    || (Iopb = QuadPart->Iopb, (unsigned __int8)(Iopb->MajorFunction - 3) <= 1u) && Iopb->MinorFunction == 2
    || (v4 = FltLockUserBuffer(QuadPart), v4 >= 0) )
  {
    if ( BYTE6(Entry[15].QuadPart) )
    {
      SqospDestroyJob(Entry);
      v5 = 0;
      v6 = FLT_PREOP_SUCCESS_NO_CALLBACK;
    }
    else
    {
      v5 = Entry;
      v6 = FLT_PREOP_SUCCESS_WITH_CALLBACK;
    }
    FltCompletePendedPreOperation(QuadPart, v6, v5);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_febed84a0cc4351c39ee11633478a7cb_Traceguids,
        (unsigned int)v4);
    }
    SqospFailJob(Entry, v4);
  }
}

```

## disassembly

```asm
0x140006a38  mov     [rsp+arg_0], rbx
0x140006a3d  mov     [rsp+arg_8], rsi
0x140006a42  push    rdi
0x140006a43  sub     rsp, 20h
0x140006a47  mov     rdi, [rcx]
0x140006a4a  mov     rbx, rcx
0x140006a4d  mov     eax, [rdi]
0x140006a4f  test    al, 8
0x140006a51  jnz     short loc_140006AC0
0x140006a53  mov     rcx, [rdi+10h]
0x140006a57  mov     al, [rcx+4]
0x140006a5a  sub     al, 3
0x140006a5c  cmp     al, 1
0x140006a5e  ja      short loc_140006A66
0x140006a60  cmp     byte ptr [rcx+5], 2
0x140006a64  jz      short loc_140006AC0
0x140006a66  mov     rcx, rdi; CallbackData
0x140006a69  call    cs:__imp_FltLockUserBuffer
0x140006a70  nop     dword ptr [rax+rax+00h]
0x140006a75  mov     esi, eax
0x140006a77  test    eax, eax
0x140006a79  jns     short loc_140006AC0
0x140006a7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140006a82  lea     rax, WPP_GLOBAL_Control
0x140006a89  cmp     rcx, rax
0x140006a8c  jz      short loc_140006AB4
0x140006a8e  mov     edx, [rcx+2Ch]
0x140006a91  test    dl, 8
0x140006a94  jz      short loc_140006AB4
0x140006a96  cmp     byte ptr [rcx+29h], 2
0x140006a9a  jb      short loc_140006AB4
0x140006a9c  mov     rcx, [rcx+18h]
0x140006aa0  lea     r8, WPP_febed84a0cc4351c39ee11633478a7cb_Traceguids
0x140006aa7  mov     edx, 0Ah
0x140006aac  mov     r9d, esi
0x140006aaf  call    WPP_SF_d
0x140006ab4  mov     edx, esi
0x140006ab6  mov     rcx, rbx; Entry
0x140006ab9  call    SqospFailJob
0x140006abe  jmp     short loc_140006AEB
0x140006ac0  cmp     byte ptr [rbx+7Eh], 0
0x140006ac4  jz      short loc_140006AD7
0x140006ac6  mov     rcx, rbx; Entry
0x140006ac9  call    SqospDestroyJob
0x140006ace  xor     r8d, r8d
0x140006ad1  lea     edx, [r8+1]
0x140006ad5  jmp     short loc_140006ADC
0x140006ad7  mov     r8, rbx; Context
0x140006ada  xor     edx, edx; CallbackStatus
0x140006adc  mov     rcx, rdi; CallbackData
0x140006adf  call    cs:__imp_FltCompletePendedPreOperation
0x140006ae6  nop     dword ptr [rax+rax+00h]
0x140006aeb  mov     rbx, [rsp+28h+arg_0]
0x140006af0  mov     rsi, [rsp+28h+arg_8]
0x140006af5  add     rsp, 20h
0x140006af9  pop     rdi
0x140006afa  retn
```
