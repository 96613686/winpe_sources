# UnionFs::Utils::CombinePathNoRealloc(_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING &,UnionFs::StackEventTracer &,ushort const *)

- ea: `0x14006a554`
- end: `0x14006a743`
- name: `?CombinePathNoRealloc@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@0AEAU3@AEAVStackEventTracer@2@PEBG@Z`
- size: `495`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, PCUNICODE_STRING Source, const struct _UNICODE_STRING *this, struct _UNICODE_STRING *, struct _UNICODE_STRING *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14006a3cc`
- `0x1400785b8`

## callees

- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x14006a554`
- `0x14006a74c`
- `0x14007843c`
- `0x14007af90`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14006a6c2`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14006a6c2`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14006a6da`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14006a6da`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14006a608`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14006a644`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14006a608`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14006a644`

## string_xrefs

- `0x14006a590`: `PUSH: ComputeCombinedPathLength`
- `0x14006a6ec`: `Couldn't append name component`
- `0x14006a5c9`: `ORIGIN: CombinedPath too small`
- `0x14006a5a1`: `UnionFs::Utils::CombinePathNoRealloc`
- `0x14006a5dc`: `UnionFs::Utils::CombinePathNoRealloc`
- `0x14006a709`: `UnionFs::Utils::CombinePathNoRealloc`
- `0x14006a6f8`: `API: Constructing CombinedPath`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::CombinePathNoRealloc(
        PCUNICODE_STRING SourceString,
        PCUNICODE_STRING Source,
        struct _UNICODE_STRING *this,
        struct _UNICODE_STRING *a4,
        struct _UNICODE_STRING *a5)
{
  USHORT Length; // dx
  int v9; // r14d
  int v10; // ebp
  unsigned int v12; // edx
  unsigned __int64 v13; // r8
  WCHAR v14; // r9
  bool v15; // dl
  NTSTATUS appended; // edi
  char *v17; // [rsp+20h] [rbp-48h]
  const char *v18; // [rsp+28h] [rbp-40h]
  unsigned __int16 v19; // [rsp+70h] [rbp+8h] BYREF

  this->Length = 0;
  Length = Source->Length;
  v19 = 0;
  v9 = (int)a4;
  v10 = UnionFs::Utils::ComputeCombinedPathLength(
          (UnionFs::Utils *)SourceString->Length,
          Length,
          (unsigned __int16)&v19,
          &a4->Length,
          (struct UnionFs::StackEventTracer *)v17);
  if ( v10 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v10,
      v9,
      (struct UnionFs::StackEventTracer *)0x49400210482LL,
      (unsigned __int64)"UnionFs::Utils::CombinePathNoRealloc",
      "PUSH: ComputeCombinedPathLength",
      v18);
    return (unsigned int)v10;
  }
  if ( this->MaximumLength < v19 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0000023LL,
      v9,
      (struct UnionFs::StackEventTracer *)0x4FE00210488LL,
      (unsigned __int64)"UnionFs::Utils::CombinePathNoRealloc",
      "ORIGIN: CombinedPath too small",
      v18);
    return 3221225507LL;
  }
  if ( SourceString->Length )
  {
    RtlCopyUnicodeString(this, SourceString);
    if ( Source->Length )
    {
      v14 = *Source->Buffer;
      if ( v14 != 92 || Source->Length != 2 )
      {
        v13 = this->Length;
        v15 = 0;
        if ( this->Buffer[(v13 >> 1) - 1] == 92 )
        {
          if ( v14 == 92 )
          {
            LOWORD(v13) = v13 - 2;
            this->Length = v13;
          }
        }
        else
        {
          v15 = v14 != 92;
        }
        if ( Source->Length )
        {
          if ( v15 && (appended = RtlAppendUnicodeToString(this, L"\\"), appended < 0)
            || (appended = RtlAppendUnicodeStringToString(this, Source), appended < 0) )
          {
            MicrosoftTelemetryAssertTriggeredMsgKM("Couldn't append name component");
            UnionFs::ProcessTraceStatusFromApi(
              (UnionFs *)(unsigned int)appended,
              v9,
              (struct UnionFs::StackEventTracer *)0x2F0002104CALL,
              (unsigned __int64)"UnionFs::Utils::CombinePathNoRealloc",
              "API: Constructing CombinedPath",
              v18);
            return (unsigned int)appended;
          }
        }
      }
    }
    UnionFs::Utils::StripTrailingBackslashFromPath((UnionFs::Utils *)this, a5, (const unsigned __int16 *)v13);
  }
  else
  {
    RtlCopyUnicodeString(this, Source);
    v12 = this->Length;
    if ( v12 > 2 && this->Buffer[((unsigned __int64)this->Length >> 1) - 1] == 92 )
      this->Length = v12 - 2;
  }
  return 0;
}

```

## disassembly

```asm
0x14006a554  push    rbx
0x14006a556  push    rbp
0x14006a557  push    rsi
0x14006a558  push    rdi
0x14006a559  push    r14
0x14006a55b  push    r15
0x14006a55d  sub     rsp, 38h
0x14006a561  xor     r15d, r15d
0x14006a564  mov     rbx, r8
0x14006a567  mov     [r8], r15w
0x14006a56b  mov     rsi, rdx
0x14006a56e  movzx   edx, word ptr [rdx]; unsigned __int16
0x14006a571  lea     r8, [rsp+68h+arg_0]; unsigned __int16
0x14006a576  mov     rdi, rcx
0x14006a579  mov     [rsp+68h+arg_0], r15w
0x14006a57f  movzx   ecx, word ptr [rcx]; this
0x14006a582  mov     r14, r9
0x14006a585  call    ?ComputeCombinedPathLength@Utils@UnionFs@@YAJGGPEAGAEAVStackEventTracer@2@@Z; UnionFs::Utils::ComputeCombinedPathLength(ushort,ushort,ushort *,UnionFs::StackEventTracer &)
0x14006a58a  mov     ebp, eax
0x14006a58c  test    eax, eax
0x14006a58e  jns     short loc_14006A5BE
0x14006a590  lea     rax, aPushComputecom_0; "PUSH: ComputeCombinedPathLength"
0x14006a597  mov     r8, 49400210482h; struct UnionFs::StackEventTracer *
0x14006a5a1  lea     r9, aUnionfsUtilsCo_1; "UnionFs::Utils::CombinePathNoRealloc"
0x14006a5a8  mov     [rsp+68h+var_48], rax; char *
0x14006a5ad  mov     rdx, r14; int
0x14006a5b0  mov     ecx, ebp; this
0x14006a5b2  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006a5b7  mov     eax, ebp
0x14006a5b9  jmp     loc_14006A735
0x14006a5be  movzx   eax, [rsp+68h+arg_0]
0x14006a5c3  cmp     [rbx+2], ax
0x14006a5c7  jnb     short loc_14006A5FC
0x14006a5c9  lea     rax, aOriginCombined; "ORIGIN: CombinedPath too small"
0x14006a5d0  mov     ebx, 0C0000023h
0x14006a5d5  mov     ecx, ebx; this
0x14006a5d7  mov     [rsp+68h+var_48], rax; char *
0x14006a5dc  lea     r9, aUnionfsUtilsCo_1; "UnionFs::Utils::CombinePathNoRealloc"
0x14006a5e3  mov     r8, 4FE00210488h; struct UnionFs::StackEventTracer *
0x14006a5ed  mov     rdx, r14; int
0x14006a5f0  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006a5f5  mov     eax, ebx
0x14006a5f7  jmp     loc_14006A735
0x14006a5fc  mov     rcx, rbx; DestinationString
0x14006a5ff  cmp     [rdi], r15w
0x14006a603  jnz     short loc_14006A641
0x14006a605  mov     rdx, rsi; SourceString
0x14006a608  call    cs:__imp_RtlCopyUnicodeString
0x14006a60f  nop     dword ptr [rax+rax+00h]
0x14006a614  movzx   edx, word ptr [rbx]
0x14006a617  cmp     edx, 2
0x14006a61a  jbe     loc_14006A733
0x14006a620  mov     rax, [rbx+8]
0x14006a624  mov     ecx, edx
0x14006a626  shr     rcx, 1
0x14006a629  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x14006a62f  jnz     loc_14006A733
0x14006a635  sub     dx, 2
0x14006a639  mov     [rbx], dx
0x14006a63c  jmp     loc_14006A733
0x14006a641  mov     rdx, rdi; SourceString
0x14006a644  call    cs:__imp_RtlCopyUnicodeString
0x14006a64b  nop     dword ptr [rax+rax+00h]
0x14006a650  movzx   ecx, word ptr [rsi]
0x14006a653  test    cx, cx
0x14006a656  jz      loc_14006A723
0x14006a65c  mov     rax, [rsi+8]
0x14006a660  movzx   r9d, word ptr [rax]
0x14006a664  cmp     r9w, 5Ch ; '\'
0x14006a669  jnz     short loc_14006A675
0x14006a66b  cmp     cx, 2
0x14006a66f  jz      loc_14006A723
0x14006a675  movzx   r8d, word ptr [rbx]
0x14006a679  mov     rax, [rbx+8]
0x14006a67d  mov     ecx, r8d
0x14006a680  shr     rcx, 1
0x14006a683  movzx   edx, r15b
0x14006a687  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x14006a68d  jnz     short loc_14006A6A1
0x14006a68f  cmp     r9w, 5Ch ; '\'
0x14006a694  jnz     short loc_14006A6AE
0x14006a696  sub     r8w, 2
0x14006a69b  mov     [rbx], r8w
0x14006a69f  jmp     short loc_14006A6AE
0x14006a6a1  cmp     r9w, 5Ch ; '\'
0x14006a6a6  mov     eax, 1
0x14006a6ab  cmovnz  edx, eax
0x14006a6ae  cmp     [rsi], r15w
0x14006a6b2  jz      short loc_14006A723
0x14006a6b4  test    dl, dl
0x14006a6b6  jz      short loc_14006A6D4
0x14006a6b8  lea     rdx, Source; "\\"
0x14006a6bf  mov     rcx, rbx; Destination
0x14006a6c2  call    cs:__imp_RtlAppendUnicodeToString
0x14006a6c9  nop     dword ptr [rax+rax+00h]
0x14006a6ce  mov     edi, eax
0x14006a6d0  test    eax, eax
0x14006a6d2  js      short loc_14006A6EC
0x14006a6d4  mov     rdx, rsi; Source
0x14006a6d7  mov     rcx, rbx; Destination
0x14006a6da  call    cs:__imp_RtlAppendUnicodeStringToString
0x14006a6e1  nop     dword ptr [rax+rax+00h]
0x14006a6e6  mov     edi, eax
0x14006a6e8  test    eax, eax
0x14006a6ea  jns     short loc_14006A723
0x14006a6ec  lea     rcx, aCouldnTAppendN; "Couldn't append name component"
0x14006a6f3  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14006a6f8  lea     rax, aApiConstructin_1; "API: Constructing CombinedPath"
0x14006a6ff  mov     r8, 2F0002104CAh; struct UnionFs::StackEventTracer *
0x14006a709  lea     r9, aUnionfsUtilsCo_1; "UnionFs::Utils::CombinePathNoRealloc"
0x14006a710  mov     [rsp+68h+var_48], rax; char *
0x14006a715  mov     rdx, r14; int
0x14006a718  mov     ecx, edi; this
0x14006a71a  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006a71f  mov     eax, edi
0x14006a721  jmp     short loc_14006A735
0x14006a723  mov     rdx, [rsp+68h+arg_20]; struct _UNICODE_STRING *
0x14006a72b  mov     rcx, rbx; this
0x14006a72e  call    ?StripTrailingBackslashFromPath@Utils@UnionFs@@YAXAEAU_UNICODE_STRING@@PEBG@Z; UnionFs::Utils::StripTrailingBackslashFromPath(_UNICODE_STRING &,ushort const *)
0x14006a733  xor     eax, eax
0x14006a735  add     rsp, 38h
0x14006a739  pop     r15
0x14006a73b  pop     r14
0x14006a73d  pop     rdi
0x14006a73e  pop     rsi
0x14006a73f  pop     rbp
0x14006a740  pop     rbx
0x14006a741  retn
```
