# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1800057b4`
- end: `0x180005970`
- name: `??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U4@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@6AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `444`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004f70`
- `0x18000e8a8`

## callees

- `0x1800057b4`
- `0x180008a90`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000591f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000591f`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        const unsigned __int16 **a6,
        __int64 *a7,
        __int64 **a8,
        __int64 a9,
        __int64 a10,
        __int64 a11)
{
  __int64 v13; // rdx
  __int64 *v14; // rcx
  __int64 v15; // rax
  int v16; // eax
  const unsigned __int16 *v17; // rcx
  __int64 v18; // rax
  int v19; // eax
  const unsigned __int16 *v20; // rcx
  int v21; // edx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-99h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-81h] BYREF
  unsigned __int8 *v25; // [rsp+60h] [rbp-71h]
  int v26; // [rsp+68h] [rbp-69h]
  int v27; // [rsp+6Ch] [rbp-65h]
  const unsigned __int16 *v28; // [rsp+70h] [rbp-61h]
  int v29; // [rsp+78h] [rbp-59h]
  int v30; // [rsp+7Ch] [rbp-55h]
  const unsigned __int16 *v31; // [rsp+80h] [rbp-51h]
  int v32; // [rsp+88h] [rbp-49h]
  int v33; // [rsp+8Ch] [rbp-45h]
  __int64 v34; // [rsp+90h] [rbp-41h]
  __int64 v35; // [rsp+98h] [rbp-39h]
  __int64 *v36; // [rsp+A0h] [rbp-31h]
  int v37; // [rsp+A8h] [rbp-29h]
  int v38; // [rsp+ACh] [rbp-25h]
  __int64 v39; // [rsp+B0h] [rbp-21h]
  __int64 v40; // [rsp+B8h] [rbp-19h]
  __int64 v41; // [rsp+C0h] [rbp-11h]
  __int64 v42; // [rsp+C8h] [rbp-9h]
  __int64 v43; // [rsp+D0h] [rbp-1h]
  __int64 v44; // [rsp+D8h] [rbp+7h]

  v43 = a11;
  v41 = a10;
  v13 = -1;
  v39 = a9;
  v44 = 8;
  v42 = 4;
  v40 = 4;
  v14 = *a8;
  if ( *a8 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *((_WORD *)v14 + v15) );
    v16 = 2 * v15 + 2;
  }
  else
  {
    v14 = &qword_180022030;
    v16 = 2;
  }
  v37 = v16;
  v36 = v14;
  v38 = 0;
  v35 = 16;
  v34 = *a7;
  v17 = *a6;
  if ( *a6 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *((_BYTE *)v17 + v18) );
    v19 = v18 + 1;
  }
  else
  {
    v17 = &dword_18002202C;
    v19 = 1;
  }
  v32 = v19;
  v31 = v17;
  v33 = 0;
  v20 = *a5;
  if ( *a5 )
  {
    do
      ++v13;
    while ( *((_BYTE *)v20 + v13) );
    v21 = v13 + 1;
  }
  else
  {
    v20 = &dword_18002202C;
    v21 = 1;
  }
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v28 = v20;
  v29 = v21;
  v30 = 0;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v26 = *(unsigned __int16 *)(a2 + 11);
  v25 = a2 + 11;
  UserData.Reserved = 2;
  v27 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, 9u, &UserData);
}

```

## disassembly

```asm
0x1800057b4  push    rbp
0x1800057b6  lea     rbp, [rsp-1Fh]
0x1800057bb  sub     rsp, 0F0h
0x1800057c2  mov     rax, cs:__security_cookie
0x1800057c9  xor     rax, rsp
0x1800057cc  mov     [rbp+1Fh+var_10], rax
0x1800057d0  mov     rax, [rbp+1Fh+arg_50]
0x1800057d4  mov     r8, rdx
0x1800057d7  mov     [rbp+1Fh+var_20], rax
0x1800057db  mov     r10, rcx
0x1800057de  mov     rax, [rbp+1Fh+arg_48]
0x1800057e2  xor     r9d, r9d; RelatedActivityId
0x1800057e5  mov     [rbp+1Fh+var_30], rax
0x1800057e9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800057ed  mov     rax, [rbp+1Fh+arg_40]
0x1800057f1  mov     [rbp+1Fh+var_40], rax
0x1800057f5  mov     rax, [rbp+1Fh+arg_38]
0x1800057f9  mov     [rbp+1Fh+var_18], 8
0x180005801  mov     [rbp+1Fh+var_28], 4
0x180005809  mov     [rbp+1Fh+var_38], 4
0x180005811  mov     rcx, [rax]
0x180005814  test    rcx, rcx
0x180005817  jz      loc_180005941
0x18000581d  mov     rax, rdx
0x180005820  inc     rax
0x180005823  cmp     [rcx+rax*2], r9w
0x180005828  jnz     short loc_180005820
0x18000582a  lea     eax, ds:2[rax*2]
0x180005831  mov     [rbp+1Fh+var_48], eax
0x180005834  mov     r11d, 1
0x18000583a  mov     rax, [rbp+1Fh+arg_30]
0x18000583e  mov     [rbp+1Fh+var_50], rcx
0x180005842  mov     [rbp+1Fh+var_44], r9d
0x180005846  mov     [rbp+1Fh+var_58], 10h
0x18000584e  mov     rcx, [rax]
0x180005851  mov     rax, [rbp+1Fh+arg_28]
0x180005855  mov     [rbp+1Fh+var_60], rcx
0x180005859  mov     rcx, [rax]
0x18000585c  test    rcx, rcx
0x18000585f  jz      loc_180005952
0x180005865  mov     rax, rdx
0x180005868  inc     rax
0x18000586b  cmp     [rcx+rax], r9b
0x18000586f  jnz     short loc_180005868
0x180005871  inc     eax
0x180005873  mov     [rbp+1Fh+var_68], eax
0x180005876  mov     rax, [rbp+1Fh+arg_20]
0x18000587a  mov     [rbp+1Fh+var_70], rcx
0x18000587e  mov     [rbp+1Fh+var_64], r9d
0x180005882  mov     rcx, [rax]
0x180005885  test    rcx, rcx
0x180005888  jz      loc_180005961
0x18000588e  inc     rdx
0x180005891  cmp     [rcx+rdx], r9b
0x180005895  jnz     short loc_18000588E
0x180005897  inc     edx
0x180005899  movzx   eax, byte ptr [r8]
0x18000589d  shl     eax, 18h
0x1800058a0  mov     dword ptr [rsp+0F0h+EventDescriptor.Id], eax
0x1800058a4  movzx   eax, word ptr [r8+1]
0x1800058a9  mov     dword ptr [rsp+0F0h+EventDescriptor.Level], eax
0x1800058ad  mov     rax, [r8+3]
0x1800058b1  mov     [rsp+0F0h+EventDescriptor.Keyword], rax
0x1800058b6  mov     rax, [r10+8]
0x1800058ba  mov     [rsp+0F0h+var_A0.Ptr], rax
0x1800058bf  mov     [rbp+1Fh+var_80], rcx
0x1800058c3  lea     rcx, [r8+0Bh]
0x1800058c7  mov     [rbp+1Fh+var_78], edx
0x1800058ca  xor     r8d, r8d; ActivityId
0x1800058cd  mov     [rbp+1Fh+var_74], r9d
0x1800058d1  lea     rdx, [rsp+0F0h+EventDescriptor]; EventDescriptor
0x1800058d6  movzx   eax, word ptr [rax]
0x1800058d9  mov     [rbp+1Fh+var_A0.Size], eax
0x1800058dc  movzx   eax, word ptr [rcx]
0x1800058df  mov     [rbp+1Fh+var_88], eax
0x1800058e2  lea     rax, _TraceLoggingMetadataEnd
0x1800058e9  mov     [rbp+1Fh+var_90], rcx
0x1800058ed  lea     rcx, _TraceLoggingMetadata
0x1800058f4  sub     eax, ecx
0x1800058f6  mov     dword ptr [rbp+1Fh+var_A0.0Ch], 2
0x1800058fd  mov     [rbp+1Fh+var_84], r11d
0x180005901  mov     [rsp+0F0h+var_C0], eax
0x180005905  mov     eax, [rsp+0F0h+var_C0]
0x180005909  mov     rcx, [r10+20h]; RegHandle
0x18000590d  lea     rax, [rsp+0F0h+var_A0]
0x180005912  mov     [rsp+0F0h+UserData], rax; UserData
0x180005917  mov     [rsp+0F0h+UserDataCount], 9; UserDataCount
0x18000591f  call    cs:__imp_EventWriteTransfer
0x180005926  nop     dword ptr [rax+rax+00h]
0x18000592b  mov     rcx, [rbp+1Fh+var_10]
0x18000592f  xor     rcx, rsp; StackCookie
0x180005932  call    __security_check_cookie
0x180005937  add     rsp, 0F0h
0x18000593e  pop     rbp
0x18000593f  retn
0x180005941  lea     rcx, qword_180022030
0x180005948  mov     eax, 2
0x18000594d  jmp     loc_180005831
0x180005952  lea     rcx, dword_18002202C
0x180005959  mov     eax, r11d
0x18000595c  jmp     loc_180005873
0x180005961  lea     rcx, dword_18002202C
0x180005968  mov     edx, r11d
0x18000596b  jmp     loc_180005899
```
