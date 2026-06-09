# OncRpcSeCreateOutboundGssContext

- ea: `0x140008d78`
- end: `0x140008f52`
- name: `OncRpcSeCreateOutboundGssContext`
- size: `474`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140006bb0`

## callees

- `0x1400020c0`
- `0x140008d78`
- `0x140012838`
- `0x140015b40`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140008e9f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140008eb6`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140008e9f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140008eb6`
- `ntoskrnl!KeInitializeMutex` at `0x140008ecb`
- `ntoskrnl!KeInitializeMutex` at `0x140008ecb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008ef2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008f06`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008ef2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008f06`

## pseudocode

```c
__int64 __fastcall OncRpcSeCreateOutboundGssContext(__int64 a1, _QWORD *a2, int a3, void **a4)
{
  int v8; // edi
  _WORD *v9; // rcx
  char *v10; // r9
  wchar_t *v11; // rax
  __int16 v12; // si
  void *v13; // rcx
  UNICODE_STRING Source; // [rsp+20h] [rbp-48h] BYREF
  UNICODE_STRING v16; // [rsp+30h] [rbp-38h] BYREF

  *(_QWORD *)&Source.Length = 655368;
  Source.Buffer = L"nfs/";
  v16 = 0;
  v8 = NfsMemMgrBufferAllocate(512, 1129269074, 224, a4);
  if ( v8 < 0 )
    goto LABEL_14;
  memset(*a4, 0, 0xE0u);
  v9 = *a4;
  v9[4] = 0;
  *((_QWORD *)v9 + 2) = 0;
  *(_DWORD *)v9 = 1129269074;
  *((_DWORD *)v9 + 1) = 0;
  *((_DWORD *)*a4 + 15) &= ~1u;
  *((_DWORD *)*a4 + 15) &= ~2u;
  *((_DWORD *)*a4 + 16) = 0;
  *((_QWORD *)*a4 + 23) = *a2;
  *((_DWORD *)*a4 + 30) = a3;
  v10 = (char *)*a4;
  v11 = (wchar_t *)(*(_QWORD *)(a1 + 8) + 2LL);
  v16.Length = *(_WORD *)a1 - 2;
  v16.Buffer = v11;
  LOWORD(v11) = *(_WORD *)(a1 + 2);
  v12 = Source.Length + v16.Length;
  v16.MaximumLength = (_WORD)v11 - 2;
  v8 = NfsMemMgrBufferAllocate(512, 1349470034, (unsigned __int16)(Source.Length + v16.Length), v10 + 200);
  if ( v8 < 0 )
  {
LABEL_14:
    if ( *a4 )
    {
      v13 = (void *)*((_QWORD *)*a4 + 25);
      if ( v13 )
        ExFreePoolWithTag(v13, 0x506F4752u);
      ExFreePoolWithTag(*a4, 0x434F4752u);
    }
  }
  else
  {
    *((_WORD *)*a4 + 96) = 0;
    *((_WORD *)*a4 + 97) = v12;
    RtlAppendUnicodeStringToString((PUNICODE_STRING)*a4 + 12, &Source);
    RtlAppendUnicodeStringToString((PUNICODE_STRING)*a4 + 12, &v16);
    KeInitializeMutex((PRKMUTEX)((char *)*a4 + 128), 0);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 73, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140008d78  push    rbx
0x140008d7a  push    rbp
0x140008d7b  push    rsi
0x140008d7c  push    rdi
0x140008d7d  push    r14
0x140008d7f  sub     rsp, 40h
0x140008d83  mov     ebp, r8d
0x140008d86  mov     qword ptr [rsp+68h+Source.Length], 0A0008h
0x140008d8f  mov     r14, rdx
0x140008d92  lea     rax, aNfs; "nfs/"
0x140008d99  mov     rsi, rcx
0x140008d9c  mov     [rsp+68h+Source.Buffer], rax
0x140008da1  xorps   xmm0, xmm0
0x140008da4  mov     edx, 434F4752h
0x140008da9  mov     ecx, 200h
0x140008dae  mov     r8d, 0E0h
0x140008db4  movups  xmmword ptr [rsp+68h+var_38.Length], xmm0
0x140008db9  mov     rbx, r9
0x140008dbc  call    NfsMemMgrBufferAllocate
0x140008dc1  mov     edi, eax
0x140008dc3  test    eax, eax
0x140008dc5  js      loc_140008ED9
0x140008dcb  mov     rcx, [rbx]; void *
0x140008dce  xor     edx, edx; Val
0x140008dd0  mov     r8d, 0E0h; Size
0x140008dd6  call    memset
0x140008ddb  mov     rcx, [rbx]
0x140008dde  xor     eax, eax
0x140008de0  mov     r8d, 2
0x140008de6  mov     [rcx+8], ax
0x140008dea  mov     qword ptr [rcx+10h], 0
0x140008df2  mov     dword ptr [rcx], 434F4752h
0x140008df8  mov     dword ptr [rcx+4], 0
0x140008dff  mov     rax, [rbx]
0x140008e02  and     dword ptr [rax+3Ch], 0FFFFFFFEh
0x140008e06  mov     rax, [rbx]
0x140008e09  and     dword ptr [rax+3Ch], 0FFFFFFFDh
0x140008e0d  mov     rax, [rbx]
0x140008e10  mov     dword ptr [rax+40h], 0
0x140008e17  mov     rcx, [rbx]
0x140008e1a  mov     rax, [r14]
0x140008e1d  mov     [rcx+0B8h], rax
0x140008e24  mov     ecx, 200h
0x140008e29  mov     rax, [rbx]
0x140008e2c  mov     [rax+78h], ebp
0x140008e2f  movzx   edx, word ptr [rsi]
0x140008e32  mov     rax, [rsi+8]
0x140008e36  sub     dx, r8w
0x140008e3a  mov     r9, [rbx]
0x140008e3d  add     rax, r8
0x140008e40  mov     [rsp+68h+var_38.Length], dx
0x140008e45  add     r9, 0C8h
0x140008e4c  add     dx, [rsp+68h+Source.Length]
0x140008e51  mov     [rsp+68h+var_38.Buffer], rax
0x140008e56  movzx   eax, word ptr [rsi+2]
0x140008e5a  movzx   esi, dx
0x140008e5d  sub     ax, r8w
0x140008e61  mov     r8d, esi
0x140008e64  mov     [rsp+68h+var_38.MaximumLength], ax
0x140008e69  mov     edx, 506F4752h
0x140008e6e  call    NfsMemMgrBufferAllocate
0x140008e73  mov     edi, eax
0x140008e75  test    eax, eax
0x140008e77  js      short loc_140008ED9
0x140008e79  mov     rcx, [rbx]
0x140008e7c  lea     rdx, [rsp+68h+Source]; Source
0x140008e81  xor     eax, eax
0x140008e83  mov     [rcx+0C0h], ax
0x140008e8a  mov     rax, [rbx]
0x140008e8d  mov     [rax+0C2h], si
0x140008e94  mov     esi, 0C0h
0x140008e99  mov     rcx, [rbx]
0x140008e9c  add     rcx, rsi; Destination
0x140008e9f  call    cs:__imp_RtlAppendUnicodeStringToString
0x140008ea6  nop     dword ptr [rax+rax+00h]
0x140008eab  mov     rcx, [rbx]
0x140008eae  lea     rdx, [rsp+68h+var_38]; Source
0x140008eb3  add     rcx, rsi; Destination
0x140008eb6  call    cs:__imp_RtlAppendUnicodeStringToString
0x140008ebd  nop     dword ptr [rax+rax+00h]
0x140008ec2  mov     rcx, [rbx]
0x140008ec5  xor     edx, edx; Level
0x140008ec7  sub     rcx, 0FFFFFFFFFFFFFF80h; Mutex
0x140008ecb  call    cs:__imp_KeInitializeMutex
0x140008ed2  nop     dword ptr [rax+rax+00h]
0x140008ed7  jmp     short loc_140008F12
0x140008ed9  mov     rax, [rbx]
0x140008edc  test    rax, rax
0x140008edf  jz      short loc_140008F12
0x140008ee1  mov     rcx, [rax+0C8h]; P
0x140008ee8  test    rcx, rcx
0x140008eeb  jz      short loc_140008EFE
0x140008eed  mov     edx, 506F4752h; Tag
0x140008ef2  call    cs:__imp_ExFreePoolWithTag
0x140008ef9  nop     dword ptr [rax+rax+00h]
0x140008efe  mov     rcx, [rbx]; P
0x140008f01  mov     edx, 434F4752h; Tag
0x140008f06  call    cs:__imp_ExFreePoolWithTag
0x140008f0d  nop     dword ptr [rax+rax+00h]
0x140008f12  mov     rcx, cs:WPP_GLOBAL_Control
0x140008f19  lea     rax, WPP_GLOBAL_Control
0x140008f20  cmp     rcx, rax
0x140008f23  jz      short loc_140008F44
0x140008f25  mov     eax, [rcx+2Ch]
0x140008f28  test    al, 1
0x140008f2a  jz      short loc_140008F44
0x140008f2c  mov     rcx, [rcx+18h]
0x140008f30  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x140008f37  mov     edx, 49h ; 'I'
0x140008f3c  mov     r9d, edi
0x140008f3f  call    WPP_SF_d
0x140008f44  mov     eax, edi
0x140008f46  add     rsp, 40h
0x140008f4a  pop     r14
0x140008f4c  pop     rdi
0x140008f4d  pop     rsi
0x140008f4e  pop     rbp
0x140008f4f  pop     rbx
0x140008f50  retn
```
