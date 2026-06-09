# ProfileImagePathQueryRoutine(ushort *,ulong,void *,ulong,void *,void *)

- ea: `0x140004c50`
- end: `0x140004e25`
- name: `?ProfileImagePathQueryRoutine@@YAJPEAGKPEAXK11@Z`
- size: `469`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, void *, unsigned int, void *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140003944`
- `0x140004c50`
- `0x14000dd24`

## import_xrefs

- `ntoskrnl!FsRtlDissectName` at `0x140004cf7`
- `ntoskrnl!FsRtlDissectName` at `0x140004d33`
- `ntoskrnl!FsRtlDissectName` at `0x140004cf7`
- `ntoskrnl!FsRtlDissectName` at `0x140004d33`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004dbf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004dd7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004dbf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004dd7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140004d61`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140004d61`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140004d0e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140004d0e`

## pseudocode

```c
__int64 __fastcall ProfileImagePathQueryRoutine(unsigned __int16 *a1, int a2, wchar_t *a3, unsigned int a4)
{
  unsigned int v4; // edi
  unsigned __int16 v5; // cx
  char *PoolWithTag; // rax
  _QWORD *v7; // rbx
  void *v8; // rcx
  struct _UNICODE_STRING RemainingName; // [rsp+20h] [rbp-50h] BYREF
  UNICODE_STRING String2; // [rsp+30h] [rbp-40h] BYREF
  UNICODE_STRING SourceString; // [rsp+40h] [rbp-30h] BYREF
  struct _UNICODE_STRING FirstName; // [rsp+50h] [rbp-20h] BYREF
  UNICODE_STRING Path; // [rsp+60h] [rbp-10h] BYREF

  if ( a3 && a4 )
  {
    v4 = 0;
    if ( (unsigned int)(a2 - 1) > 1 && a2 != 7 )
      return v4;
    v5 = a4;
    if ( !a3[((unsigned __int64)a4 >> 1) - 1] )
      LOWORD(a4) = a4 - 2;
    *(_QWORD *)&String2.Length = 786442;
    String2.Buffer = L"Users";
    RemainingName.Length = a4;
    RemainingName.MaximumLength = v5;
    *(_DWORD *)(&RemainingName.MaximumLength + 1) = 0;
    RemainingName.Buffer = a3;
    SourceString = 0;
    if ( (_WORD)a4 )
    {
      while ( !SourceString.Length )
      {
        Path = RemainingName;
        FirstName = 0;
        FsRtlDissectName(&Path, &FirstName, &RemainingName);
        if ( RtlEqualUnicodeString(&FirstName, &String2, 1u) )
        {
          Path = RemainingName;
          FsRtlDissectName(&Path, &SourceString, &RemainingName);
        }
        if ( !RemainingName.Length )
          goto LABEL_12;
      }
    }
    else
    {
LABEL_12:
      if ( !SourceString.Length )
        return v4;
    }
    PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1025, 0x18u, 0x6E6D7377u);
    v7 = PoolWithTag;
    if ( ExPoolZeroingNativelySupported )
    {
      if ( PoolWithTag )
      {
LABEL_16:
        v4 = Duplicate(&SourceString, (PUNICODE_STRING)(PoolWithTag + 8));
        if ( (v4 & 0x80000000) == 0 )
        {
          *v7 = qword_140019420;
          qword_140019420 = v7;
        }
        else
        {
          WriteLogMessage(3, L"Failed to duplicate user name for new privacy entry");
          v8 = (void *)v7[2];
          if ( v8 )
          {
            ExFreePoolWithTag(v8, 0x6E6D7377u);
            v7[2] = 0;
          }
          ExFreePoolWithTag(v7, 0x6E6D7377u);
        }
        return v4;
      }
    }
    else if ( PoolWithTag )
    {
      *(_OWORD *)PoolWithTag = 0;
      *((_QWORD *)PoolWithTag + 2) = 0;
      goto LABEL_16;
    }
    WriteLogMessage(3, L"Failed to allocate memory for a new privacy entry");
    return (unsigned int)-1073741670;
  }
  return 0;
}

```

## disassembly

```asm
0x140004c50  push    rbp
0x140004c52  push    rbx
0x140004c53  push    rsi
0x140004c54  push    rdi
0x140004c55  push    r14
0x140004c57  mov     rbp, rsp
0x140004c5a  sub     rsp, 70h
0x140004c5e  xor     r14d, r14d
0x140004c61  test    r8, r8
0x140004c64  jz      loc_140004E17
0x140004c6a  test    r9d, r9d
0x140004c6d  jz      loc_140004E17
0x140004c73  lea     eax, [rdx-1]
0x140004c76  mov     edi, r14d
0x140004c79  cmp     eax, 1
0x140004c7c  jbe     short loc_140004C87
0x140004c7e  cmp     edx, 7
0x140004c81  jnz     loc_140004E13
0x140004c87  mov     eax, r9d
0x140004c8a  xor     edx, edx
0x140004c8c  shr     rax, 1
0x140004c8f  movzx   ecx, r9w
0x140004c93  cmp     [r8+rax*2-2], r14w
0x140004c99  jnz     short loc_140004CA4
0x140004c9b  mov     eax, 0FFFEh
0x140004ca0  add     r9w, ax
0x140004ca4  mov     qword ptr [rbp+String2.Length], 0C000Ah
0x140004cac  lea     rax, aUsers; "Users"
0x140004cb3  mov     [rbp+String2.Buffer], rax
0x140004cb7  xorps   xmm0, xmm0
0x140004cba  mov     [rbp+RemainingName.Length], r9w
0x140004cbf  mov     [rbp+RemainingName.MaximumLength], cx
0x140004cc3  mov     dword ptr [rbp+RemainingName+4], edx
0x140004cc6  mov     [rbp+RemainingName.Buffer], r8
0x140004cca  movups  xmmword ptr [rbp+SourceString.Length], xmm0
0x140004cce  test    r9w, r9w
0x140004cd2  jz      short loc_140004D46
0x140004cd4  cmp     [rbp+SourceString.Length], r14w
0x140004cd9  jnz     short loc_140004D51
0x140004cdb  movaps  xmm1, xmmword ptr [rbp+RemainingName.Length]
0x140004cdf  lea     r8, [rbp+RemainingName]; RemainingName
0x140004ce3  xorps   xmm0, xmm0
0x140004ce6  movdqa  xmmword ptr [rbp+Path.Length], xmm1
0x140004ceb  lea     rdx, [rbp+FirstName]; FirstName
0x140004cef  lea     rcx, [rbp+Path]; Path
0x140004cf3  movups  xmmword ptr [rbp+FirstName.Length], xmm0
0x140004cf7  call    cs:__imp_FsRtlDissectName
0x140004cfe  nop     dword ptr [rax+rax+00h]
0x140004d03  mov     r8b, 1; CaseInSensitive
0x140004d06  lea     rdx, [rbp+String2]; String2
0x140004d0a  lea     rcx, [rbp+FirstName]; String1
0x140004d0e  call    cs:__imp_RtlEqualUnicodeString
0x140004d15  nop     dword ptr [rax+rax+00h]
0x140004d1a  test    al, al
0x140004d1c  jz      short loc_140004D3F
0x140004d1e  movaps  xmm0, xmmword ptr [rbp+RemainingName.Length]
0x140004d22  lea     r8, [rbp+RemainingName]; RemainingName
0x140004d26  lea     rdx, [rbp+SourceString]; FirstName
0x140004d2a  movdqa  xmmword ptr [rbp+Path.Length], xmm0
0x140004d2f  lea     rcx, [rbp+Path]; Path
0x140004d33  call    cs:__imp_FsRtlDissectName
0x140004d3a  nop     dword ptr [rax+rax+00h]
0x140004d3f  cmp     [rbp+RemainingName.Length], r14w
0x140004d44  ja      short loc_140004CD4
0x140004d46  cmp     [rbp+SourceString.Length], r14w
0x140004d4b  jz      loc_140004E13
0x140004d51  mov     edx, 18h; NumberOfBytes
0x140004d56  mov     ecx, 401h; PoolType
0x140004d5b  mov     r8d, 6E6D7377h; Tag
0x140004d61  call    cs:__imp_ExAllocatePoolWithTag
0x140004d68  nop     dword ptr [rax+rax+00h]
0x140004d6d  cmp     cs:ExPoolZeroingNativelySupported, r14b
0x140004d74  mov     rbx, rax
0x140004d77  jnz     short loc_140004DE5
0x140004d79  test    rax, rax
0x140004d7c  jz      short loc_140004DEA
0x140004d7e  xorps   xmm0, xmm0
0x140004d81  xor     eax, eax
0x140004d83  movups  xmmword ptr [rbx], xmm0
0x140004d86  mov     [rbx+10h], rax
0x140004d8a  lea     rdx, [rbx+8]; DestinationString
0x140004d8e  mov     rsi, rbx
0x140004d91  lea     rcx, [rbp+SourceString]; SourceString
0x140004d95  call    ?Duplicate@@YAJPEBU_UNICODE_STRING@@PEAU1@@Z; Duplicate(_UNICODE_STRING const *,_UNICODE_STRING *)
0x140004d9a  mov     edi, eax
0x140004d9c  test    eax, eax
0x140004d9e  jns     short loc_140004E02
0x140004da0  lea     rdx, aFailedToDuplic_1; "Failed to duplicate user name for new p"...
0x140004da7  mov     ecx, 3
0x140004dac  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140004db1  mov     rcx, [rbx+10h]; P
0x140004db5  test    rcx, rcx
0x140004db8  jz      short loc_140004DCF
0x140004dba  mov     edx, 6E6D7377h; Tag
0x140004dbf  call    cs:__imp_ExFreePoolWithTag
0x140004dc6  nop     dword ptr [rax+rax+00h]
0x140004dcb  mov     [rbx+10h], r14
0x140004dcf  mov     edx, 6E6D7377h; Tag
0x140004dd4  mov     rcx, rsi; P
0x140004dd7  call    cs:__imp_ExFreePoolWithTag
0x140004dde  nop     dword ptr [rax+rax+00h]
0x140004de3  jmp     short loc_140004E13
0x140004de5  test    rbx, rbx
0x140004de8  jnz     short loc_140004D8A
0x140004dea  lea     rdx, aFailedToAlloca_12; "Failed to allocate memory for a new pri"...
0x140004df1  mov     ecx, 3
0x140004df6  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140004dfb  mov     edi, 0C000009Ah
0x140004e00  jmp     short loc_140004E13
0x140004e02  mov     rax, cs:qword_140019420
0x140004e09  mov     [rbx], rax
0x140004e0c  mov     cs:qword_140019420, rbx
0x140004e13  mov     eax, edi
0x140004e15  jmp     short loc_140004E19
0x140004e17  xor     eax, eax
0x140004e19  add     rsp, 70h
0x140004e1d  pop     r14
0x140004e1f  pop     rdi
0x140004e20  pop     rsi
0x140004e21  pop     rbx
0x140004e22  pop     rbp
0x140004e23  retn
```
