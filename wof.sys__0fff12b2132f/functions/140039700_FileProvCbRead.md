# FileProvCbRead

- ea: `0x140039700`
- end: `0x140039a47`
- name: `FileProvCbRead`
- size: `839`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA Data@<rcx>, __int64, char, __int64, int, void *, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140007878`
- `0x140007a30`
- `0x140007a50`
- `0x140008df0`
- `0x14000d3b8`
- `0x14000fb60`
- `0x1400119c0`
- `0x140039700`

## import_xrefs

- `ntoskrnl!KeQueryPriorityThread` at `0x1400397e8`
- `ntoskrnl!KeQueryPriorityThread` at `0x1400397e8`
- `ntoskrnl!ExAcquireFastMutex` at `0x140039972`
- `ntoskrnl!ExAcquireFastMutex` at `0x140039972`
- `ntoskrnl!ExReleaseFastMutex` at `0x140039984`
- `ntoskrnl!ExReleaseFastMutex` at `0x140039984`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140039861`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140039861`
- `FLTMGR!FltGetIoPriorityHintFromCallbackData` at `0x140039814`
- `FLTMGR!FltGetIoPriorityHintFromCallbackData` at `0x140039814`

## pseudocode

```c
__int64 __fastcall FileProvCbRead(
        PFLT_CALLBACK_DATA Data,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        char a6,
        __int64 a7,
        unsigned int a8,
        void *a9,
        __int64 a10,
        _QWORD *a11)
{
  char v14; // r14
  NTSTATUS Parameters; // eax
  unsigned int *v16; // rbx
  NTSTATUS v17; // edi
  __int64 v18; // rcx
  char IsMdlInvariant; // al
  BOOL v20; // eax
  __int64 v21; // rdi
  PVOID FsContext; // rbx
  __int64 v24; // rbp
  __int64 v25; // rsi
  size_t v26; // r8
  __int64 v27; // rbx
  PVOID Parameter[5]; // [rsp+30h] [rbp-28h] BYREF

  Parameter[0] = 0;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_3ab28fa3c8e53516c82f52d1da45ff3e_Traceguids);
  if ( *(_QWORD *)(a5 + 40) )
  {
    if ( *(_QWORD *)(a5 + 16) )
    {
      v14 = 0;
      Parameters = FileProvAllocateReadParameters(a5, Parameter);
      v16 = (unsigned int *)Parameter[0];
      v17 = Parameters;
      if ( !Parameters )
      {
        *(_QWORD *)Parameter[0] = Data;
        v18 = a3;
        v14 = 1;
        if ( !a6 )
          v18 = 0;
        *((_QWORD *)v16 + 1) = v18;
        *((_QWORD *)v16 + 2) = a4;
        *((_QWORD *)v16 + 3) = a7;
        *((_QWORD *)v16 + 7) = a9;
        if ( a10 )
          IsMdlInvariant = WofIsMdlInvariant();
        else
          IsMdlInvariant = 0;
        *((_BYTE *)v16 + 68) = IsMdlInvariant;
        v16[12] = a8;
        *((_QWORD *)v16 + 4) = a5;
        v16[18] = KeQueryPriorityThread(KeGetCurrentThread());
        v20 = !a6 || !a3;
        v16[19] = v20;
        if ( Data )
          v16[16] = FltGetIoPriorityHintFromCallbackData(Data);
        else
          v16[16] = 2;
        v21 = FileProvCompressionScheme(*((_QWORD *)v16 + 4));
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_3b099794e4b93327e327da255c047df6_Traceguids);
        v17 = KeExpandKernelStackAndCalloutEx(FileProvReadCompressedCallout, v16, 0x4000u, 0, *(PVOID *)(v21 + 768));
        if ( v17 >= 0 )
          v17 = v16[20];
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            13,
            WPP_3b099794e4b93327e327da255c047df6_Traceguids,
            (unsigned int)v17);
      }
      if ( v17 >= 0 && v17 != 259 )
        *a11 = v16[13];
      if ( v14 )
        FileProvReleaseReadCbReadParameters(v16);
      goto LABEL_22;
    }
    FsContext = Data->Iopb->TargetFileObject->FsContext;
    if ( (*((_BYTE *)FsContext + 4) & 0x40) != 0 )
      ExAcquireFastMutex(*((PFAST_MUTEX *)FsContext + 6));
    v24 = *((_QWORD *)FsContext + 5);
    v25 = *((_QWORD *)FsContext + 4);
    if ( (*((_BYTE *)FsContext + 4) & 0x40) != 0 )
      ExReleaseFastMutex(*((PFAST_MUTEX *)FsContext + 6));
    if ( a7 >= v24 )
    {
      if ( a7 < v25 )
      {
        v26 = a8;
        if ( a7 + a8 >= v25 )
          v26 = (unsigned int)(v25 - a7);
        if ( (_DWORD)v26 )
        {
          v27 = (unsigned int)v26;
          memset(a9, 0, v26);
          goto LABEL_34;
        }
      }
      else
      {
        LODWORD(v26) = 0;
      }
      v27 = (unsigned int)v26;
LABEL_34:
      *a11 = v27;
      return 0;
    }
  }
  v17 = -1073740690;
LABEL_22:
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_3ab28fa3c8e53516c82f52d1da45ff3e_Traceguids, (unsigned int)v17);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x140039700  mov     [rsp+arg_18], rbp
0x140039705  push    rsi
0x140039706  push    r12
0x140039708  push    r15
0x14003970a  sub     rsp, 40h
0x14003970e  mov     r15, r9
0x140039711  mov     [rsp+58h+Parameter], 0
0x14003971a  mov     r12, r8
0x14003971d  mov     rbp, rcx
0x140039720  mov     rcx, cs:WPP_GLOBAL_Control
0x140039727  mov     eax, [rcx+2Ch]
0x14003972a  test    al, 20h
0x14003972c  jnz     loc_140039940
0x140039732  mov     rsi, [rsp+58h+arg_20]
0x14003973a  mov     [rsp+58h+arg_0], rbx
0x14003973f  mov     [rsp+58h+arg_8], rdi
0x140039744  cmp     qword ptr [rsi+28h], 0
0x140039749  jz      loc_140039964
0x14003974f  cmp     qword ptr [rsi+10h], 0
0x140039754  jz      loc_1400398F2
0x14003975a  mov     [rsp+58h+arg_10], r14
0x14003975f  lea     rdx, [rsp+58h+Parameter]
0x140039764  mov     rcx, rsi
0x140039767  xor     r14b, r14b
0x14003976a  call    FileProvAllocateReadParameters
0x14003976f  mov     rbx, [rsp+58h+Parameter]
0x140039774  mov     edi, eax
0x140039776  test    eax, eax
0x140039778  jnz     loc_140039888
0x14003977e  movzx   edi, [rsp+58h+arg_28]
0x140039786  xor     eax, eax
0x140039788  mov     [rbx], rbp
0x14003978b  test    dil, dil
0x14003978e  mov     rcx, r12
0x140039791  mov     r14b, 1
0x140039794  cmovz   rcx, rax
0x140039798  mov     rax, [rsp+58h+arg_30]
0x1400397a0  mov     [rbx+8], rcx
0x1400397a4  mov     rcx, [rsp+58h+arg_48]
0x1400397ac  mov     [rbx+10h], r15
0x1400397b0  mov     [rbx+18h], rax
0x1400397b4  mov     rax, [rsp+58h+arg_40]
0x1400397bc  mov     [rbx+38h], rax
0x1400397c0  test    rcx, rcx
0x1400397c3  jz      loc_140039939
0x1400397c9  call    WofIsMdlInvariant
0x1400397ce  mov     [rbx+44h], al
0x1400397d1  mov     eax, [rsp+58h+arg_38]
0x1400397d8  mov     [rbx+30h], eax
0x1400397db  mov     [rbx+20h], rsi
0x1400397df  mov     rcx, gs:188h; Thread
0x1400397e8  call    cs:__imp_KeQueryPriorityThread
0x1400397ef  nop     dword ptr [rax+rax+00h]
0x1400397f4  mov     [rbx+48h], eax
0x1400397f7  test    dil, dil
0x1400397fa  jnz     loc_1400398E2
0x140039800  mov     eax, 1
0x140039805  mov     [rbx+4Ch], eax
0x140039808  test    rbp, rbp
0x14003980b  jz      loc_1400399C9
0x140039811  mov     rcx, rbp; Data
0x140039814  call    cs:__imp_FltGetIoPriorityHintFromCallbackData
0x14003981b  nop     dword ptr [rax+rax+00h]
0x140039820  mov     [rbx+40h], eax
0x140039823  mov     rcx, [rbx+20h]
0x140039827  call    FileProvCompressionScheme
0x14003982c  mov     rdi, rax
0x14003982f  mov     rcx, cs:WPP_GLOBAL_Control
0x140039836  mov     edx, [rcx+2Ch]
0x140039839  test    dl, 20h
0x14003983c  jnz     loc_1400399D5
0x140039842  mov     rax, [rdi+300h]
0x140039849  lea     rcx, FileProvReadCompressedCallout; Callout
0x140039850  xor     r9d, r9d; Wait
0x140039853  mov     [rsp+58h+Context], rax; Context
0x140039858  mov     r8d, 4000h; Size
0x14003985e  mov     rdx, rbx; Parameter
0x140039861  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x140039868  nop     dword ptr [rax+rax+00h]
0x14003986d  mov     edi, eax
0x14003986f  test    eax, eax
0x140039871  js      short loc_140039876
0x140039873  mov     edi, [rbx+50h]
0x140039876  mov     rcx, cs:WPP_GLOBAL_Control
0x14003987d  mov     eax, [rcx+2Ch]
0x140039880  test    al, 20h
0x140039882  jnz     loc_1400399F9
0x140039888  test    edi, edi
0x14003988a  js      short loc_1400398A2
0x14003988c  cmp     edi, 103h
0x140039892  jz      short loc_1400398A2
0x140039894  mov     rax, [rsp+58h+arg_50]
0x14003989c  mov     ecx, [rbx+34h]
0x14003989f  mov     [rax], rcx
0x1400398a2  test    r14b, r14b
0x1400398a5  mov     r14, [rsp+58h+arg_10]
0x1400398aa  jz      short loc_1400398B4
0x1400398ac  mov     rcx, rbx
0x1400398af  call    FileProvReleaseReadCbReadParameters
0x1400398b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400398bb  mov     eax, [rcx+2Ch]
0x1400398be  test    al, 20h
0x1400398c0  jnz     loc_140039A20
0x1400398c6  mov     eax, edi
0x1400398c8  mov     rdi, [rsp+58h+arg_8]
0x1400398cd  mov     rbx, [rsp+58h+arg_0]
0x1400398d2  mov     rbp, [rsp+58h+arg_18]
0x1400398d7  add     rsp, 40h
0x1400398db  pop     r15
0x1400398dd  pop     r12
0x1400398df  pop     rsi
0x1400398e0  retn
0x1400398e2  test    r12, r12
0x1400398e5  jz      loc_140039800
0x1400398eb  xor     eax, eax
0x1400398ed  jmp     loc_140039805
0x1400398f2  mov     rax, [rbp+10h]
0x1400398f6  mov     rcx, [rax+8]
0x1400398fa  mov     rbx, [rcx+18h]
0x1400398fe  test    byte ptr [rbx+4], 40h
0x140039902  jnz     short loc_14003996E
0x140039904  test    byte ptr [rbx+4], 40h
0x140039908  mov     rbp, [rbx+28h]
0x14003990c  mov     rsi, [rbx+20h]
0x140039910  jnz     short loc_140039980
0x140039912  mov     rax, [rsp+58h+arg_30]
0x14003991a  cmp     rax, rbp
0x14003991d  jl      short loc_140039964
0x14003991f  cmp     rax, rsi
0x140039922  jl      short loc_140039992
0x140039924  xor     r8d, r8d
0x140039927  mov     ebx, r8d
0x14003992a  mov     rax, [rsp+58h+arg_50]
0x140039932  mov     [rax], rbx
0x140039935  xor     eax, eax
0x140039937  jmp     short loc_1400398C8
0x140039939  xor     al, al
0x14003993b  jmp     loc_1400397CE
0x140039940  cmp     byte ptr [rcx+29h], 4
0x140039944  jb      loc_140039732
0x14003994a  mov     rcx, [rcx+18h]
0x14003994e  lea     r8, WPP_3ab28fa3c8e53516c82f52d1da45ff3e_Traceguids
0x140039955  mov     edx, 0Dh
0x14003995a  call    WPP_SF_
0x14003995f  jmp     loc_140039732
0x140039964  mov     edi, 0C000046Eh
0x140039969  jmp     loc_1400398B4
0x14003996e  mov     rcx, [rbx+30h]; FastMutex
0x140039972  call    cs:__imp_ExAcquireFastMutex
0x140039979  nop     dword ptr [rax+rax+00h]
0x14003997e  jmp     short loc_140039904
0x140039980  mov     rcx, [rbx+30h]; FastMutex
0x140039984  call    cs:__imp_ExReleaseFastMutex
0x14003998b  nop     dword ptr [rax+rax+00h]
0x140039990  jmp     short loc_140039912
0x140039992  mov     r8d, [rsp+58h+arg_38]
0x14003999a  lea     rdx, [rax+r8]
0x14003999e  cmp     rdx, rsi
0x1400399a1  jl      short loc_1400399A9
0x1400399a3  mov     r8d, esi
0x1400399a6  sub     r8d, eax; Size
0x1400399a9  test    r8d, r8d
0x1400399ac  jz      loc_140039927
0x1400399b2  mov     rcx, [rsp+58h+arg_40]; void *
0x1400399ba  xor     edx, edx; Val
0x1400399bc  mov     ebx, r8d
0x1400399bf  call    memset
0x1400399c4  jmp     loc_14003992A
0x1400399c9  mov     dword ptr [rbx+40h], 2
0x1400399d0  jmp     loc_140039823
0x1400399d5  cmp     byte ptr [rcx+29h], 4
0x1400399d9  jb      loc_140039842
0x1400399df  mov     rcx, [rcx+18h]
0x1400399e3  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x1400399ea  mov     edx, 0Ch
0x1400399ef  call    WPP_SF_
0x1400399f4  jmp     loc_140039842
0x1400399f9  cmp     byte ptr [rcx+29h], 4
0x1400399fd  jb      loc_140039888
0x140039a03  mov     rcx, [rcx+18h]
0x140039a07  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140039a0e  mov     edx, 0Dh
0x140039a13  mov     r9d, edi
0x140039a16  call    WPP_SF_d
0x140039a1b  jmp     loc_140039888
0x140039a20  cmp     byte ptr [rcx+29h], 4
0x140039a24  jb      loc_1400398C6
0x140039a2a  mov     rcx, [rcx+18h]
0x140039a2e  lea     r8, WPP_3ab28fa3c8e53516c82f52d1da45ff3e_Traceguids
0x140039a35  mov     edx, 0Eh
0x140039a3a  mov     r9d, edi
0x140039a3d  call    WPP_SF_d
0x140039a42  jmp     loc_1400398C6
```
