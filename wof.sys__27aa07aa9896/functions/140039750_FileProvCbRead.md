# FileProvCbRead

- ea: `0x140039750`
- end: `0x140039a97`
- name: `FileProvCbRead`
- size: `839`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data, __int64, __int64, __int64, __int64, char, __int64, unsigned int, void *, __int64, _QWORD *)`
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
- `0x140039750`

## import_xrefs

- `ntoskrnl!KeQueryPriorityThread` at `0x140039838`
- `ntoskrnl!KeQueryPriorityThread` at `0x140039838`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400399c2`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400399c2`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400399d4`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400399d4`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1400398b1`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1400398b1`
- `FLTMGR!FltGetIoPriorityHintFromCallbackData` at `0x140039864`
- `FLTMGR!FltGetIoPriorityHintFromCallbackData` at `0x140039864`

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
0x140039750  mov     [rsp+arg_18], rbp
0x140039755  push    rsi
0x140039756  push    r12
0x140039758  push    r15
0x14003975a  sub     rsp, 40h
0x14003975e  mov     r15, r9
0x140039761  mov     [rsp+58h+Parameter], 0
0x14003976a  mov     r12, r8
0x14003976d  mov     rbp, rcx
0x140039770  mov     rcx, cs:WPP_GLOBAL_Control
0x140039777  mov     eax, [rcx+2Ch]
0x14003977a  test    al, 20h
0x14003977c  jnz     loc_140039990
0x140039782  mov     rsi, [rsp+58h+arg_20]
0x14003978a  mov     [rsp+58h+arg_0], rbx
0x14003978f  mov     [rsp+58h+arg_8], rdi
0x140039794  cmp     qword ptr [rsi+28h], 0
0x140039799  jz      loc_1400399B4
0x14003979f  cmp     qword ptr [rsi+10h], 0
0x1400397a4  jz      loc_140039942
0x1400397aa  mov     [rsp+58h+arg_10], r14
0x1400397af  lea     rdx, [rsp+58h+Parameter]
0x1400397b4  mov     rcx, rsi
0x1400397b7  xor     r14b, r14b
0x1400397ba  call    FileProvAllocateReadParameters
0x1400397bf  mov     rbx, [rsp+58h+Parameter]
0x1400397c4  mov     edi, eax
0x1400397c6  test    eax, eax
0x1400397c8  jnz     loc_1400398D8
0x1400397ce  movzx   edi, [rsp+58h+arg_28]
0x1400397d6  xor     eax, eax
0x1400397d8  mov     [rbx], rbp
0x1400397db  test    dil, dil
0x1400397de  mov     rcx, r12
0x1400397e1  mov     r14b, 1
0x1400397e4  cmovz   rcx, rax
0x1400397e8  mov     rax, [rsp+58h+arg_30]
0x1400397f0  mov     [rbx+8], rcx
0x1400397f4  mov     rcx, [rsp+58h+arg_48]
0x1400397fc  mov     [rbx+10h], r15
0x140039800  mov     [rbx+18h], rax
0x140039804  mov     rax, [rsp+58h+arg_40]
0x14003980c  mov     [rbx+38h], rax
0x140039810  test    rcx, rcx
0x140039813  jz      loc_140039989
0x140039819  call    WofIsMdlInvariant
0x14003981e  mov     [rbx+44h], al
0x140039821  mov     eax, [rsp+58h+arg_38]
0x140039828  mov     [rbx+30h], eax
0x14003982b  mov     [rbx+20h], rsi
0x14003982f  mov     rcx, gs:188h; Thread
0x140039838  call    cs:__imp_KeQueryPriorityThread
0x14003983f  nop     dword ptr [rax+rax+00h]
0x140039844  mov     [rbx+48h], eax
0x140039847  test    dil, dil
0x14003984a  jnz     loc_140039932
0x140039850  mov     eax, 1
0x140039855  mov     [rbx+4Ch], eax
0x140039858  test    rbp, rbp
0x14003985b  jz      loc_140039A19
0x140039861  mov     rcx, rbp; Data
0x140039864  call    cs:__imp_FltGetIoPriorityHintFromCallbackData
0x14003986b  nop     dword ptr [rax+rax+00h]
0x140039870  mov     [rbx+40h], eax
0x140039873  mov     rcx, [rbx+20h]
0x140039877  call    FileProvCompressionScheme
0x14003987c  mov     rdi, rax
0x14003987f  mov     rcx, cs:WPP_GLOBAL_Control
0x140039886  mov     edx, [rcx+2Ch]
0x140039889  test    dl, 20h
0x14003988c  jnz     loc_140039A25
0x140039892  mov     rax, [rdi+300h]
0x140039899  lea     rcx, FileProvReadCompressedCallout; Callout
0x1400398a0  xor     r9d, r9d; Wait
0x1400398a3  mov     [rsp+58h+Context], rax; Context
0x1400398a8  mov     r8d, 4000h; Size
0x1400398ae  mov     rdx, rbx; Parameter
0x1400398b1  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x1400398b8  nop     dword ptr [rax+rax+00h]
0x1400398bd  mov     edi, eax
0x1400398bf  test    eax, eax
0x1400398c1  js      short loc_1400398C6
0x1400398c3  mov     edi, [rbx+50h]
0x1400398c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400398cd  mov     eax, [rcx+2Ch]
0x1400398d0  test    al, 20h
0x1400398d2  jnz     loc_140039A49
0x1400398d8  test    edi, edi
0x1400398da  js      short loc_1400398F2
0x1400398dc  cmp     edi, 103h
0x1400398e2  jz      short loc_1400398F2
0x1400398e4  mov     rax, [rsp+58h+arg_50]
0x1400398ec  mov     ecx, [rbx+34h]
0x1400398ef  mov     [rax], rcx
0x1400398f2  test    r14b, r14b
0x1400398f5  mov     r14, [rsp+58h+arg_10]
0x1400398fa  jz      short loc_140039904
0x1400398fc  mov     rcx, rbx
0x1400398ff  call    FileProvReleaseReadCbReadParameters
0x140039904  mov     rcx, cs:WPP_GLOBAL_Control
0x14003990b  mov     eax, [rcx+2Ch]
0x14003990e  test    al, 20h
0x140039910  jnz     loc_140039A70
0x140039916  mov     eax, edi
0x140039918  mov     rdi, [rsp+58h+arg_8]
0x14003991d  mov     rbx, [rsp+58h+arg_0]
0x140039922  mov     rbp, [rsp+58h+arg_18]
0x140039927  add     rsp, 40h
0x14003992b  pop     r15
0x14003992d  pop     r12
0x14003992f  pop     rsi
0x140039930  retn
0x140039932  test    r12, r12
0x140039935  jz      loc_140039850
0x14003993b  xor     eax, eax
0x14003993d  jmp     loc_140039855
0x140039942  mov     rax, [rbp+10h]
0x140039946  mov     rcx, [rax+8]
0x14003994a  mov     rbx, [rcx+18h]
0x14003994e  test    byte ptr [rbx+4], 40h
0x140039952  jnz     short loc_1400399BE
0x140039954  test    byte ptr [rbx+4], 40h
0x140039958  mov     rbp, [rbx+28h]
0x14003995c  mov     rsi, [rbx+20h]
0x140039960  jnz     short loc_1400399D0
0x140039962  mov     rax, [rsp+58h+arg_30]
0x14003996a  cmp     rax, rbp
0x14003996d  jl      short loc_1400399B4
0x14003996f  cmp     rax, rsi
0x140039972  jl      short loc_1400399E2
0x140039974  xor     r8d, r8d
0x140039977  mov     ebx, r8d
0x14003997a  mov     rax, [rsp+58h+arg_50]
0x140039982  mov     [rax], rbx
0x140039985  xor     eax, eax
0x140039987  jmp     short loc_140039918
0x140039989  xor     al, al
0x14003998b  jmp     loc_14003981E
0x140039990  cmp     byte ptr [rcx+29h], 4
0x140039994  jb      loc_140039782
0x14003999a  mov     rcx, [rcx+18h]
0x14003999e  lea     r8, WPP_3ab28fa3c8e53516c82f52d1da45ff3e_Traceguids
0x1400399a5  mov     edx, 0Dh
0x1400399aa  call    WPP_SF_
0x1400399af  jmp     loc_140039782
0x1400399b4  mov     edi, 0C000046Eh
0x1400399b9  jmp     loc_140039904
0x1400399be  mov     rcx, [rbx+30h]; FastMutex
0x1400399c2  call    cs:__imp_ExAcquireFastMutex
0x1400399c9  nop     dword ptr [rax+rax+00h]
0x1400399ce  jmp     short loc_140039954
0x1400399d0  mov     rcx, [rbx+30h]; FastMutex
0x1400399d4  call    cs:__imp_ExReleaseFastMutex
0x1400399db  nop     dword ptr [rax+rax+00h]
0x1400399e0  jmp     short loc_140039962
0x1400399e2  mov     r8d, [rsp+58h+arg_38]
0x1400399ea  lea     rdx, [rax+r8]
0x1400399ee  cmp     rdx, rsi
0x1400399f1  jl      short loc_1400399F9
0x1400399f3  mov     r8d, esi
0x1400399f6  sub     r8d, eax; Size
0x1400399f9  test    r8d, r8d
0x1400399fc  jz      loc_140039977
0x140039a02  mov     rcx, [rsp+58h+arg_40]; void *
0x140039a0a  xor     edx, edx; Val
0x140039a0c  mov     ebx, r8d
0x140039a0f  call    memset
0x140039a14  jmp     loc_14003997A
0x140039a19  mov     dword ptr [rbx+40h], 2
0x140039a20  jmp     loc_140039873
0x140039a25  cmp     byte ptr [rcx+29h], 4
0x140039a29  jb      loc_140039892
0x140039a2f  mov     rcx, [rcx+18h]
0x140039a33  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140039a3a  mov     edx, 0Ch
0x140039a3f  call    WPP_SF_
0x140039a44  jmp     loc_140039892
0x140039a49  cmp     byte ptr [rcx+29h], 4
0x140039a4d  jb      loc_1400398D8
0x140039a53  mov     rcx, [rcx+18h]
0x140039a57  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140039a5e  mov     edx, 0Dh
0x140039a63  mov     r9d, edi
0x140039a66  call    WPP_SF_d
0x140039a6b  jmp     loc_1400398D8
0x140039a70  cmp     byte ptr [rcx+29h], 4
0x140039a74  jb      loc_140039916
0x140039a7a  mov     rcx, [rcx+18h]
0x140039a7e  lea     r8, WPP_3ab28fa3c8e53516c82f52d1da45ff3e_Traceguids
0x140039a85  mov     edx, 0Eh
0x140039a8a  mov     r9d, edi
0x140039a8d  call    WPP_SF_d
0x140039a92  jmp     loc_140039916
```
