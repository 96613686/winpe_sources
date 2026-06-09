# OncRpcMsgStartup

- ea: `0x1400038c8`
- end: `0x140003b0e`
- name: `OncRpcMsgStartup`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140024b80`

## callees

- `0x1400020c0`
- `0x1400038c8`
- `0x140015640`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140003a5c`
- `ntoskrnl!KeInitializeSpinLock` at `0x140003a5c`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x1400039f7`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x1400039f7`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x1400039c0`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x1400039c0`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400039a7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400039a7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000397f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000397f`
- `ntoskrnl!ExAllocatePool2` at `0x140003a7a`
- `ntoskrnl!ExAllocatePool2` at `0x140003a7a`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140003934`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140003967`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140003934`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140003967`

## pseudocode

```c
__int64 OncRpcMsgStartup()
{
  NTSTATUS v0; // ebx
  void *Pool2; // rax
  unsigned int v2; // edx
  __int64 v3; // rcx
  _QWORD *v4; // rcx
  UNICODE_STRING SourceString; // [rsp+40h] [rbp-C0h] BYREF
  _STRING v7; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  char v9; // [rsp+70h] [rbp-90h] BYREF

  DestinationString = 0;
  *(_DWORD *)(&SourceString.MaximumLength + 1) = 0;
  v7 = 0;
  ExInitializeNPagedLookasideList(&stru_14001A700, 0, 0, 0x200u, 0x460u, 0x674D6458u, 0);
  ExInitializeNPagedLookasideList(&stru_14001A780, 0, 0, 0x200u, 0x28u, 0x524D6458u, 0);
  RtlInitUnicodeString(&DestinationString, L"unknown");
  *(_DWORD *)&SourceString.Length = 33423360;
  SourceString.Buffer = (wchar_t *)&v9;
  RtlCopyUnicodeString(&SourceString, &DestinationString);
  v0 = RtlDowncaseUnicodeString(&SourceString, &SourceString, 0);
  if ( v0 >= 0 )
  {
    *(_DWORD *)&v7.Length = 16515072;
    v7.Buffer = (PCHAR)qword_14001A808;
    v0 = RtlUnicodeStringToAnsiString(&v7, &SourceString, 0);
    if ( v0 >= 0 )
    {
      dword_14001A804 = v7.Length;
      *((_BYTE *)qword_14001A808 + v7.Length) = 0;
      dword_14001A800 = -1431655766;
      dword_14001A908 = -2;
      dword_14001A90C = -2;
      dword_14001A910 = 1;
      dword_14001A968 = 64;
      dword_14001A914 = -2;
      KeInitializeSpinLock(&qword_14001A958);
      Pool2 = (void *)ExAllocatePool2(64, 16LL * (unsigned int)dword_14001A968, 1414358104);
      v2 = 0;
      for ( P = Pool2; v2 < dword_14001A968; *v4 = v4 )
      {
        v3 = v2++;
        v4 = (char *)P + 16 * v3;
        v4[1] = v4;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_805c0885a8ed3962ecc38e19173d6373_Traceguids, (unsigned int)v0);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1400038c8  mov     [rsp-8+arg_0], rbx
0x1400038cd  mov     [rsp-8+arg_8], rdi
0x1400038d2  push    rbp
0x1400038d3  lea     rbp, [rsp-180h]
0x1400038db  sub     rsp, 280h
0x1400038e2  mov     rax, cs:__security_cookie
0x1400038e9  xor     rax, rsp
0x1400038ec  mov     [rbp+180h+var_10], rax
0x1400038f3  xorps   xmm0, xmm0
0x1400038f6  lea     rcx, stru_14001A700; Lookaside
0x1400038fd  xor     eax, eax
0x1400038ff  xorps   xmm1, xmm1
0x140003902  mov     [rsp+280h+Depth], ax; Depth
0x140003907  mov     ebx, 200h
0x14000390c  mov     [rsp+280h+Tag], 674D6458h; Tag
0x140003914  mov     r9d, ebx; Flags
0x140003917  xor     r8d, r8d; Free
0x14000391a  mov     [rsp+280h+Size], 460h; Size
0x140003923  xor     edx, edx; Allocate
0x140003925  movups  xmmword ptr [rsp+280h+DestinationString.Length], xmm0
0x14000392a  movups  xmmword ptr [rsp+280h+SourceString.Length], xmm1
0x14000392f  movups  xmmword ptr [rsp+280h+var_230.Length], xmm0
0x140003934  call    cs:__imp_ExInitializeNPagedLookasideList
0x14000393b  nop     dword ptr [rax+rax+00h]
0x140003940  xor     eax, eax
0x140003942  lea     rcx, stru_14001A780; Lookaside
0x140003949  mov     [rsp+280h+Depth], ax; Depth
0x14000394e  mov     r9d, ebx; Flags
0x140003951  mov     [rsp+280h+Tag], 524D6458h; Tag
0x140003959  xor     r8d, r8d; Free
0x14000395c  xor     edx, edx; Allocate
0x14000395e  mov     [rsp+280h+Size], 28h ; '('; Size
0x140003967  call    cs:__imp_ExInitializeNPagedLookasideList
0x14000396e  nop     dword ptr [rax+rax+00h]
0x140003973  lea     rdx, SourceString; "unknown"
0x14000397a  lea     rcx, [rsp+280h+DestinationString]; DestinationString
0x14000397f  call    cs:__imp_RtlInitUnicodeString
0x140003986  nop     dword ptr [rax+rax+00h]
0x14000398b  lea     rax, [rsp+280h+var_210]
0x140003990  mov     dword ptr [rsp+280h+SourceString.Length], 1FE0000h
0x140003998  lea     rdx, [rsp+280h+DestinationString]; SourceString
0x14000399d  mov     [rsp+280h+SourceString.Buffer], rax
0x1400039a2  lea     rcx, [rsp+280h+SourceString]; DestinationString
0x1400039a7  call    cs:__imp_RtlCopyUnicodeString
0x1400039ae  nop     dword ptr [rax+rax+00h]
0x1400039b3  xor     r8d, r8d; AllocateDestinationString
0x1400039b6  lea     rdx, [rsp+280h+SourceString]; SourceString
0x1400039bb  lea     rcx, [rsp+280h+SourceString]; DestinationString
0x1400039c0  call    cs:__imp_RtlDowncaseUnicodeString
0x1400039c7  nop     dword ptr [rax+rax+00h]
0x1400039cc  mov     ebx, eax
0x1400039ce  test    eax, eax
0x1400039d0  js      loc_140003AB5
0x1400039d6  lea     rdi, qword_14001A808
0x1400039dd  mov     dword ptr [rsp+280h+var_230.Length], 0FC0000h
0x1400039e5  xor     r8d, r8d; AllocateDestinationString
0x1400039e8  mov     [rsp+280h+var_230.Buffer], rdi
0x1400039ed  lea     rdx, [rsp+280h+SourceString]; SourceString
0x1400039f2  lea     rcx, [rsp+280h+var_230]; DestinationString
0x1400039f7  call    cs:__imp_RtlUnicodeStringToAnsiString
0x1400039fe  nop     dword ptr [rax+rax+00h]
0x140003a03  mov     ebx, eax
0x140003a05  test    eax, eax
0x140003a07  js      loc_140003AB5
0x140003a0d  movzx   eax, [rsp+280h+var_230.Length]
0x140003a12  lea     rcx, qword_14001A958; SpinLock
0x140003a19  mov     cs:dword_14001A804, eax
0x140003a1f  movzx   eax, [rsp+280h+var_230.Length]
0x140003a24  mov     byte ptr [rax+rdi], 0
0x140003a28  mov     eax, 0FFFFFFFEh
0x140003a2d  mov     cs:dword_14001A800, 0AAAAAAAAh
0x140003a37  mov     cs:dword_14001A908, eax
0x140003a3d  mov     cs:dword_14001A90C, eax
0x140003a43  lea     edi, [rax+42h]
0x140003a46  mov     cs:dword_14001A910, 1
0x140003a50  mov     cs:dword_14001A968, edi
0x140003a56  mov     cs:dword_14001A914, eax
0x140003a5c  call    cs:__imp_KeInitializeSpinLock
0x140003a63  nop     dword ptr [rax+rax+00h]
0x140003a68  mov     edx, cs:dword_14001A968
0x140003a6e  mov     r8d, 544D6458h
0x140003a74  shl     rdx, 4
0x140003a78  mov     ecx, edi
0x140003a7a  call    cs:__imp_ExAllocatePool2
0x140003a81  nop     dword ptr [rax+rax+00h]
0x140003a86  xor     edx, edx
0x140003a88  mov     cs:P, rax
0x140003a8f  cmp     cs:dword_14001A968, edx
0x140003a95  jbe     short loc_140003AB5
0x140003a97  mov     ecx, edx
0x140003a99  inc     edx
0x140003a9b  shl     rcx, 4
0x140003a9f  add     rcx, cs:P
0x140003aa6  mov     [rcx+8], rcx
0x140003aaa  mov     [rcx], rcx
0x140003aad  cmp     edx, cs:dword_14001A968
0x140003ab3  jb      short loc_140003A97
0x140003ab5  mov     rcx, cs:WPP_GLOBAL_Control
0x140003abc  lea     rax, WPP_GLOBAL_Control
0x140003ac3  cmp     rcx, rax
0x140003ac6  jz      short loc_140003AE7
0x140003ac8  mov     eax, [rcx+2Ch]
0x140003acb  test    al, 1
0x140003acd  jz      short loc_140003AE7
0x140003acf  mov     rcx, [rcx+18h]
0x140003ad3  lea     r8, WPP_805c0885a8ed3962ecc38e19173d6373_Traceguids
0x140003ada  mov     edx, 0Dh
0x140003adf  mov     r9d, ebx
0x140003ae2  call    WPP_SF_d
0x140003ae7  mov     eax, ebx
0x140003ae9  mov     rcx, [rbp+180h+var_10]
0x140003af0  xor     rcx, rsp; StackCookie
0x140003af3  call    __security_check_cookie
0x140003af8  lea     r11, [rsp+280h+var_s0]
0x140003b00  mov     rbx, [r11+10h]
0x140003b04  mov     rdi, [r11+18h]
0x140003b08  mov     rsp, r11
0x140003b0b  pop     rbp
0x140003b0c  retn
```
