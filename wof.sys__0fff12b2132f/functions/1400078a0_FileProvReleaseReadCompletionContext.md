# FileProvReleaseReadCompletionContext

- ea: `0x1400078a0`
- end: `0x140007a1f`
- name: `FileProvReleaseReadCompletionContext`
- size: `383`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140007878`
- `0x140038710`

## callees

- `0x1400078a0`
- `0x14000d440`
- `0x14000fb60`
- `0x140010654`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000797b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000797b`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000791c`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000791c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000799f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000799f`

## string_xrefs

- `0x1400079ea`: `(StreamContext != NULL) || (Context->ReadCompressedResource.ChunkTable == NULL)`

## pseudocode

```c
__int64 __fastcall FileProvReleaseReadCompletionContext(volatile signed __int32 *Entry)
{
  unsigned __int32 v2; // ebx
  __int64 v3; // rbp
  void *v4; // rsi
  void *v5; // r14

  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_dq(
      WPP_GLOBAL_Control->AttachedDevice,
      13,
      WPP_eaaba969f297373d9ffb29335f34480c_Traceguids,
      *((unsigned int *)Entry + 4),
      Entry);
  v2 = _InterlockedDecrement(Entry + 4);
  if ( !v2 )
  {
    v3 = *((_QWORD *)Entry + 7);
    v4 = (void *)*((_QWORD *)Entry + 26);
    v5 = (void *)*((_QWORD *)Entry + 27);
    if ( !v3 && *((_QWORD *)Entry + 23) )
      MicrosoftTelemetryAssertTriggeredMsgKM("(StreamContext != NULL) || (Context->ReadCompressedResource.ChunkTable == NULL)");
    if ( v4 )
    {
      ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)&qword_140019400[104 * *(unsigned int *)(v3 + 4)], v4);
      *((_QWORD *)Entry + 26) = 0;
    }
    else
    {
      if ( !v5 )
      {
LABEL_7:
        if ( (Entry[3] & 1) != 0 )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_eaaba969f297373d9ffb29335f34480c_Traceguids);
          ExFreeToNPagedLookasideList(
            (PNPAGED_LOOKASIDE_LIST)&qword_140019500[104 * *(unsigned int *)(*((_QWORD *)Entry + 7) + 4LL)],
            (PVOID)Entry);
        }
        return v2;
      }
      ExFreePoolWithTag(v5, 0);
    }
    *((_QWORD *)Entry + 27) = 0;
    goto LABEL_7;
  }
  return v2;
}

```

## disassembly

```asm
0x1400078a0  mov     [rsp+arg_18], rbx
0x1400078a5  push    rdi
0x1400078a6  sub     rsp, 30h
0x1400078aa  mov     rdi, rcx
0x1400078ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400078b4  mov     eax, [rcx+2Ch]
0x1400078b7  test    al, 20h
0x1400078b9  jnz     loc_1400079AF
0x1400078bf  mov     ebx, 0FFFFFFFFh
0x1400078c4  lock xadd [rdi+10h], ebx
0x1400078c9  sub     ebx, 1
0x1400078cc  jnz     loc_140007987
0x1400078d2  mov     [rsp+38h+arg_0], rbp
0x1400078d7  mov     rbp, [rdi+38h]
0x1400078db  mov     [rsp+38h+arg_8], rsi
0x1400078e0  mov     rsi, [rdi+0D0h]
0x1400078e7  mov     [rsp+38h+arg_10], r14
0x1400078ec  mov     r14, [rdi+0D8h]
0x1400078f3  test    rbp, rbp
0x1400078f6  jz      loc_1400079DC
0x1400078fc  test    rsi, rsi
0x1400078ff  jz      loc_140007995
0x140007905  mov     eax, [rbp+4]
0x140007908  mov     rdx, rsi; Entry
0x14000790b  imul    rcx, rax, 340h
0x140007912  lea     rax, qword_140019400
0x140007919  add     rcx, rax; Lookaside
0x14000791c  call    cs:__imp_ExFreeToPagedLookasideList
0x140007923  nop     dword ptr [rax+rax+00h]
0x140007928  xor     eax, eax
0x14000792a  mov     [rdi+0D0h], rax
0x140007931  mov     [rdi+0D8h], rax
0x140007938  mov     eax, [rdi+0Ch]
0x14000793b  mov     r14, [rsp+38h+arg_10]
0x140007940  mov     rsi, [rsp+38h+arg_8]
0x140007945  mov     rbp, [rsp+38h+arg_0]
0x14000794a  test    al, 1
0x14000794c  jz      short loc_140007987
0x14000794e  mov     rcx, cs:WPP_GLOBAL_Control
0x140007955  mov     eax, [rcx+2Ch]
0x140007958  test    al, 20h
0x14000795a  jnz     loc_1400079FB
0x140007960  mov     rax, [rdi+38h]
0x140007964  mov     rdx, rdi; Entry
0x140007967  mov     ecx, [rax+4]
0x14000796a  lea     rax, qword_140019500
0x140007971  imul    rcx, 340h
0x140007978  add     rcx, rax; Lookaside
0x14000797b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140007982  nop     dword ptr [rax+rax+00h]
0x140007987  mov     eax, ebx
0x140007989  mov     rbx, [rsp+38h+arg_18]
0x14000798e  add     rsp, 30h
0x140007992  pop     rdi
0x140007993  retn
0x140007995  test    r14, r14
0x140007998  jz      short loc_140007938
0x14000799a  xor     edx, edx; Tag
0x14000799c  mov     rcx, r14; P
0x14000799f  call    cs:__imp_ExFreePoolWithTag
0x1400079a6  nop     dword ptr [rax+rax+00h]
0x1400079ab  xor     eax, eax
0x1400079ad  jmp     short loc_140007931
0x1400079af  cmp     byte ptr [rcx+29h], 5
0x1400079b3  jb      loc_1400078BF
0x1400079b9  mov     rcx, [rcx+18h]
0x1400079bd  lea     r8, WPP_eaaba969f297373d9ffb29335f34480c_Traceguids
0x1400079c4  mov     r9d, [rdi+10h]
0x1400079c8  mov     edx, 0Dh
0x1400079cd  mov     [rsp+38h+var_18], rdi
0x1400079d2  call    WPP_SF_dq
0x1400079d7  jmp     loc_1400078BF
0x1400079dc  cmp     qword ptr [rdi+0B8h], 0
0x1400079e4  jz      loc_1400078FC
0x1400079ea  lea     rcx, aStreamcontextN; "(StreamContext != NULL) || (Context->Re"...
0x1400079f1  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400079f6  jmp     loc_1400078FC
0x1400079fb  cmp     byte ptr [rcx+29h], 5
0x1400079ff  jb      loc_140007960
0x140007a05  mov     rcx, [rcx+18h]
0x140007a09  lea     r8, WPP_eaaba969f297373d9ffb29335f34480c_Traceguids
0x140007a10  mov     edx, 0Eh
0x140007a15  call    WPP_SF_
0x140007a1a  jmp     loc_140007960
```
