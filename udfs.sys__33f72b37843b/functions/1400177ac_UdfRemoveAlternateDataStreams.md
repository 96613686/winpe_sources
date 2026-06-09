# UdfRemoveAlternateDataStreams

- ea: `0x1400177ac`
- end: `0x140017c01`
- name: `UdfRemoveAlternateDataStreams`
- size: `1109`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001662c`
- `0x1400316e8`

## callees

- `0x140005e80`
- `0x14000653c`
- `0x140008b0c`
- `0x14000a288`
- `0x14000b128`
- `0x14000b24c`
- `0x14000c3e8`
- `0x14000ca10`
- `0x140012308`
- `0x140016f68`
- `0x14001758c`
- `0x1400175d0`
- `0x1400177ac`
- `0x14001bc30`
- `0x14001c080`
- `0x14002cca0`
- `0x1400312c0`
- `0x14003e368`
- `0x140041110`
- `0x140041860`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140017bec`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14001df2d`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140017bec`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14001df2d`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400179ec`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400179ec`

## pseudocode

```c
char __fastcall UdfRemoveAlternateDataStreams(__int64 a1, __int64 a2)
{
  _QWORD *v4; // r13
  __int64 v5; // rcx
  int v6; // r15d
  _DWORD *v7; // rsi
  _QWORD *v9; // r12
  __int64 v10; // r9
  __int64 v11; // r8
  _QWORD *v12; // rdx
  _QWORD *i; // rcx
  _QWORD *v14; // r14
  __int64 v15; // rdx
  int v16; // r9d
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r8
  char v20; // [rsp+31h] [rbp-237h]
  _OWORD v22[2]; // [rsp+78h] [rbp-1F0h] BYREF
  __int64 v23; // [rsp+98h] [rbp-1D0h]
  int v24[100]; // [rsp+A0h] [rbp-1C8h] BYREF

  v4 = *(_QWORD **)(a2 + 136);
  memset(v24, 0, 0x188u);
  memset(v22, 0, sizeof(v22));
  v23 = 0;
  v6 = *(_DWORD *)(v4[2] + 212LL) & 0x200;
  v7 = 0;
  v20 = 0;
  if ( (int)UdfOpenStreamDirectory(a1, a2, 1u) >= 0 )
  {
    v22[0] = 0;
    UdfInitializeCompoundDirContext(v5, v24);
    *(_QWORD *)&v24[70] = 1;
    v9 = v4 + 3;
    UdfLookupInitialDirEntry(a1, v4[3], v24, 0, v6 == 0, 0);
    do
    {
      v11 = *(_QWORD *)&v24[8];
      if ( (*(_BYTE *)(*(_QWORD *)&v24[8] + 18LL) & 0xC) == 0 )
      {
        v12 = v4 + 4;
        for ( i = (_QWORD *)v4[4]; ; i = (_QWORD *)*i )
        {
          if ( i == v12 )
            goto LABEL_16;
          v14 = i - 15;
          if ( (*((_DWORD *)i + 23) & 0x200) == 0 && *((_DWORD *)v14 + 46) == *(_DWORD *)(*(_QWORD *)&v24[8] + 24LL) )
            break;
        }
        if ( i != v12 )
        {
          v15 = v14[20] - 32LL;
          *(_DWORD *)(v15 + 68) |= 2u;
          if ( *((_DWORD *)v14 + 50) )
            continue;
          LOBYTE(v10) = 1;
          LOBYTE(v11) = 1;
          UdfRemovePrefix(i, v15, v11, v10);
          goto LABEL_27;
        }
LABEL_16:
        UdfLookupFileEntryInEnumeration(a1, *v9, v24);
        if ( v7 || (v7 = ExAllocateFromPagedLookasideList(&UdfScbDataLookasideList)) != 0 )
        {
          memset(v7, 0, 0x200u);
          *v7 = 33556788;
          *((_QWORD *)v7 + 6) = *(_QWORD *)(a2 + 48);
          *((_QWORD *)v7 + 4) = *(_QWORD *)(*(_QWORD *)&v24[42] + 56LL);
          v7[53] = 1;
          *((_QWORD *)v7 + 17) = v4;
          v7[46] = *(_DWORD *)(*(_QWORD *)&v24[8] + 24LL);
          v7[47] = *(unsigned __int16 *)(*(_QWORD *)&v24[8] + 28LL);
          UdfInitializeAllocations(a1, (__int64)v7, (__int64)&v24[38], 0);
          v16 = 0;
        }
        else
        {
          v16 = -1073741670;
        }
        if ( v16 >= 0 )
        {
          v14 = v7;
LABEL_27:
          UdfPurgeAndFreeAllocationForScb(a1, v14);
          if ( !v6 )
          {
            if ( (*(_DWORD *)(*v9 + 212LL) & 2) != 0 )
              UdfPrepareModifyIcbForScb(a1, *v9, v22);
            UdfMarkFidDeleted(v17, v24);
            UdfSetDirtyFid(a1, v24);
            if ( (*(_DWORD *)(*v9 + 212LL) & 2) != 0 )
            {
              LOBYTE(v18) = 1;
              UdfFinishModifyIcb(a1, v22, v18, *v9);
            }
          }
          v20 = 1;
          continue;
        }
        if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10000000) != 0 )
        {
          WPP_SF_d(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
            17,
            WPP_3e271ebed6f63f8fe36d0f7ec1e80eae_Traceguids);
        }
        if ( v7 )
          UdfUninitializeScbMcb(v7);
      }
    }
    while ( (unsigned __int8)UdfLookupNextDirEntry(a1, *v9, (int)v24) );
    UdfCleanupCompoundDirContext(a1, v24, v19);
    if ( v6 )
      UdfPurgeAndFreeAllocationForScb(a1, *v9);
    UdfUnpinView(a1, v22);
    if ( v7 )
      ExFreeToPagedLookasideList(&UdfScbDataLookasideList, v7);
    return v20;
  }
  else
  {
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10000000) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 16, WPP_3e271ebed6f63f8fe36d0f7ec1e80eae_Traceguids);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1400177ac  mov     [rsp+arg_10], rbx
0x1400177b1  mov     [rsp+arg_18], rsi
0x1400177b6  push    rdi
0x1400177b7  push    r12
0x1400177b9  push    r13
0x1400177bb  push    r14
0x1400177bd  push    r15
0x1400177bf  sub     rsp, 240h
0x1400177c6  mov     rax, cs:__security_cookie
0x1400177cd  xor     rax, rsp
0x1400177d0  mov     [rsp+268h+var_38], rax
0x1400177d8  mov     r12, rdx
0x1400177db  mov     [rsp+268h+var_220], rdx
0x1400177e0  mov     rdi, rcx
0x1400177e3  mov     [rsp+268h+var_228], rcx
0x1400177e8  mov     [rsp+268h+var_200], rdx
0x1400177ed  mov     r13, [rdx+88h]
0x1400177f4  mov     [rsp+268h+var_208], r13
0x1400177f9  xor     edx, edx; Val
0x1400177fb  mov     r8d, 188h; Size
0x140017801  lea     rcx, [rsp+268h+var_1C8]; void *
0x140017809  call    memset
0x14001780e  xorps   xmm0, xmm0
0x140017811  xor     eax, eax
0x140017813  movups  [rsp+268h+var_1F0], xmm0
0x140017818  movups  [rsp+268h+var_1E0], xmm0
0x140017820  mov     [rsp+268h+var_1D0], rax
0x140017828  mov     rax, [r13+10h]
0x14001782c  mov     r15d, [rax+0D4h]
0x140017833  mov     [rsp+268h+var_230], r15d
0x140017838  mov     r8d, 1
0x14001783e  mov     rdx, r12
0x140017841  mov     rcx, rdi
0x140017844  call    UdfOpenStreamDirectory
0x140017849  mov     r9d, eax
0x14001784c  mov     [rsp+268h+var_234], eax
0x140017850  jmp     short loc_140017874
0x140017852  mov     rdi, [rsp+268h+var_228]
0x140017857  mov     r9d, [rdi+18h]
0x14001785b  mov     [rsp+268h+var_234], r9d
0x140017860  mov     r13, [rsp+268h+var_208]
0x140017865  mov     rax, [rsp+268h+var_200]
0x14001786a  mov     [rsp+268h+var_220], rax
0x14001786f  mov     r15d, [rsp+268h+var_230]
0x140017874  and     r15d, 200h
0x14001787b  xor     ebx, ebx
0x14001787d  mov     r14d, ebx
0x140017880  mov     [rsp+268h+var_218], rbx
0x140017885  mov     esi, ebx
0x140017887  mov     [rsp+268h+var_210], rbx
0x14001788c  mov     [rsp+268h+var_238], bl
0x140017890  mov     al, bl
0x140017892  mov     [rsp+268h+var_237], bl
0x140017896  mov     [rsp+268h+var_230], r15d
0x14001789b  test    r9d, r9d
0x14001789e  jns     short loc_1400178FF
0x1400178a0  lea     rax, WPP_GLOBAL_Control
0x1400178a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400178ae  cmp     rcx, rax
0x1400178b1  jz      short loc_1400178CF
0x1400178b3  test    dword ptr [rcx+2Ch], 10000000h
0x1400178ba  jz      short loc_1400178CF
0x1400178bc  lea     edx, [rbx+10h]
0x1400178bf  lea     r8, WPP_3e271ebed6f63f8fe36d0f7ec1e80eae_Traceguids
0x1400178c6  mov     rcx, [rcx+18h]
0x1400178ca  call    WPP_SF_d
0x1400178cf  xor     al, al
0x1400178d1  mov     rcx, [rsp+268h+var_38]
0x1400178d9  xor     rcx, rsp; StackCookie
0x1400178dc  call    __security_check_cookie
0x1400178e1  lea     r11, [rsp+268h+var_28]
0x1400178e9  mov     rbx, [r11+40h]
0x1400178ed  mov     rsi, [r11+48h]
0x1400178f1  mov     rsp, r11
0x1400178f4  pop     r15
0x1400178f6  pop     r14
0x1400178f8  pop     r13
0x1400178fa  pop     r12
0x1400178fc  pop     rdi
0x1400178fd  retn
0x1400178ff  xorps   xmm0, xmm0
0x140017902  movdqu  [rsp+268h+var_1F0], xmm0
0x140017908  lea     rdx, [rsp+268h+var_1C8]
0x140017910  call    UdfInitializeCompoundDirContext
0x140017915  mov     [rsp+268h+var_238], 1
0x14001791a  mov     [rsp+268h+var_B0], 1
0x140017926  lea     r12, [r13+18h]
0x14001792a  mov     [rsp+268h+var_1F8], r12
0x14001792f  test    r15d, r15d
0x140017932  setz    al
0x140017935  mov     [rsp+268h+var_240], ebx; int
0x140017939  mov     [rsp+268h+var_248], al; char
0x14001793d  xor     r9d, r9d
0x140017940  lea     r8, [rsp+268h+var_1C8]; int
0x140017948  mov     rdx, [r12]; int
0x14001794c  mov     rcx, rdi; int
0x14001794f  call    UdfLookupInitialDirEntry
0x140017954  mov     r8, [rsp+268h+var_1A8]
0x14001795c  test    byte ptr [r8+12h], 0Ch
0x140017961  jnz     loc_140017B8E
0x140017967  lea     rdx, [r13+20h]
0x14001796b  mov     rcx, [rdx]
0x14001796e  cmp     rcx, rdx
0x140017971  jz      short loc_1400179CC
0x140017973  lea     r14, [rcx-78h]
0x140017977  mov     [rsp+268h+var_218], r14
0x14001797c  mov     eax, [r14+0D4h]
0x140017983  bt      eax, 9
0x140017987  jb      short loc_140017996
0x140017989  mov     eax, [r8+18h]
0x14001798d  cmp     [r14+0B8h], eax
0x140017994  jz      short loc_14001799B
0x140017996  mov     rcx, [rcx]
0x140017999  jmp     short loc_14001796E
0x14001799b  cmp     rcx, rdx
0x14001799e  jz      short loc_1400179CC
0x1400179a0  mov     rdx, [r14+0A0h]
0x1400179a7  add     rdx, 0FFFFFFFFFFFFFFE0h
0x1400179ab  or      dword ptr [rdx+44h], 2
0x1400179af  cmp     [r14+0C8h], ebx
0x1400179b6  jnz     loc_140017B8E
0x1400179bc  mov     r9b, 1
0x1400179bf  mov     r8b, r9b
0x1400179c2  call    UdfRemovePrefix
0x1400179c7  jmp     loc_140017B22
0x1400179cc  lea     r8, [rsp+268h+var_1C8]
0x1400179d4  mov     rdx, [r12]
0x1400179d8  mov     rcx, rdi
0x1400179db  call    UdfLookupFileEntryInEnumeration
0x1400179e0  test    rsi, rsi
0x1400179e3  jnz     short loc_140017A15
0x1400179e5  lea     rcx, UdfScbDataLookasideList; Lookaside
0x1400179ec  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400179f3  nop     dword ptr [rax+rax+00h]
0x1400179f8  mov     rsi, rax
0x1400179fb  mov     [rsp+268h+var_210], rax
0x140017a00  test    rax, rax
0x140017a03  jnz     short loc_140017A15
0x140017a05  mov     r9d, 0C000009Ah
0x140017a0b  mov     [rsp+268h+var_234], r9d
0x140017a10  jmp     loc_140017A99
0x140017a15  xor     edx, edx; Val
0x140017a17  mov     r8d, 200h; Size
0x140017a1d  mov     rcx, rsi; void *
0x140017a20  call    memset
0x140017a25  mov     dword ptr [rsi], 2000934h
0x140017a2b  mov     rax, [rsp+268h+var_220]
0x140017a30  mov     rax, [rax+30h]
0x140017a34  mov     [rsi+30h], rax
0x140017a38  mov     rax, [rsp+268h+var_120]
0x140017a40  mov     rcx, [rax+38h]
0x140017a44  mov     [rsi+20h], rcx
0x140017a48  mov     dword ptr [rsi+0D4h], 1
0x140017a52  mov     [rsi+88h], r13
0x140017a59  mov     rax, [rsp+268h+var_1A8]
0x140017a61  mov     ecx, [rax+18h]
0x140017a64  mov     [rsi+0B8h], ecx
0x140017a6a  mov     rax, [rsp+268h+var_1A8]
0x140017a72  movzx   ecx, word ptr [rax+1Ch]
0x140017a76  mov     [rsi+0BCh], ecx
0x140017a7c  xor     r9d, r9d
0x140017a7f  lea     r8, [rsp+268h+var_130]
0x140017a87  mov     rdx, rsi
0x140017a8a  mov     rcx, rdi
0x140017a8d  call    UdfInitializeAllocations
0x140017a92  mov     r9d, ebx
0x140017a95  mov     [rsp+268h+var_234], ebx
0x140017a99  lea     rdx, WPP_GLOBAL_Control
0x140017aa0  jmp     short loc_140017ADC
0x140017aa2  mov     rdi, [rsp+268h+var_228]
0x140017aa7  mov     r9d, [rdi+18h]
0x140017aab  mov     [rsp+268h+var_234], r9d
0x140017ab0  xor     ebx, ebx
0x140017ab2  lea     rdx, WPP_GLOBAL_Control
0x140017ab9  mov     r14, [rsp+268h+var_218]
0x140017abe  mov     r13, [rsp+268h+var_208]
0x140017ac3  mov     rsi, [rsp+268h+var_210]
0x140017ac8  mov     rax, [rsp+268h+var_200]
0x140017acd  mov     [rsp+268h+var_220], rax
0x140017ad2  mov     r15d, [rsp+268h+var_230]
0x140017ad7  mov     r12, [rsp+268h+var_1F8]
0x140017adc  test    r9d, r9d
0x140017adf  jns     short loc_140017B1A
0x140017ae1  mov     rcx, cs:WPP_GLOBAL_Control
0x140017ae8  cmp     rcx, rdx
0x140017aeb  jz      short loc_140017B0B
0x140017aed  test    dword ptr [rcx+2Ch], 10000000h
0x140017af4  jz      short loc_140017B0B
0x140017af6  mov     edx, 11h
0x140017afb  lea     r8, WPP_3e271ebed6f63f8fe36d0f7ec1e80eae_Traceguids
0x140017b02  mov     rcx, [rcx+18h]
0x140017b06  call    WPP_SF_d
0x140017b0b  test    rsi, rsi
0x140017b0e  jz      short loc_140017B8E
0x140017b10  mov     rcx, rsi
0x140017b13  call    UdfUninitializeScbMcb
0x140017b18  jmp     short loc_140017B8E
0x140017b1a  mov     r14, rsi
0x140017b1d  mov     [rsp+268h+var_218], rsi
0x140017b22  mov     rdx, r14
0x140017b25  mov     rcx, rdi
0x140017b28  call    UdfPurgeAndFreeAllocationForScb
0x140017b2d  test    r15d, r15d
0x140017b30  jnz     short loc_140017B89
0x140017b32  mov     rdx, [r12]
0x140017b36  mov     eax, [rdx+0D4h]
0x140017b3c  test    al, 2
0x140017b3e  jz      short loc_140017B4D
0x140017b40  lea     r8, [rsp+268h+var_1F0]
0x140017b45  mov     rcx, rdi
0x140017b48  call    UdfPrepareModifyIcbForScb
0x140017b4d  lea     rdx, [rsp+268h+var_1C8]
0x140017b55  call    UdfMarkFidDeleted
0x140017b5a  lea     rdx, [rsp+268h+var_1C8]
0x140017b62  mov     rcx, rdi
0x140017b65  call    UdfSetDirtyFid
0x140017b6a  mov     r9, [r12]
0x140017b6e  mov     eax, [r9+0D4h]
0x140017b75  test    al, 2
0x140017b77  jz      short loc_140017B89
0x140017b79  mov     r8b, 1
0x140017b7c  lea     rdx, [rsp+268h+var_1F0]
0x140017b81  mov     rcx, rdi
0x140017b84  call    UdfFinishModifyIcb
0x140017b89  mov     [rsp+268h+var_237], 1
0x140017b8e  lea     r8, [rsp+268h+var_1C8]; int
0x140017b96  mov     rdx, [r12]; int
0x140017b9a  mov     rcx, rdi; int
0x140017b9d  call    UdfLookupNextDirEntry
0x140017ba2  test    al, al
0x140017ba4  jnz     loc_140017954
0x140017baa  lea     rdx, [rsp+268h+var_1C8]
0x140017bb2  mov     rcx, rdi
0x140017bb5  call    UdfCleanupCompoundDirContext
0x140017bba  mov     [rsp+268h+var_238], bl
0x140017bbe  test    r15d, r15d
0x140017bc1  jz      short loc_140017BD0
0x140017bc3  mov     rdx, [r12]
0x140017bc7  mov     rcx, rdi
0x140017bca  call    UdfPurgeAndFreeAllocationForScb
0x140017bcf  nop
0x140017bd0  lea     rdx, [rsp+268h+var_1F0]
0x140017bd5  mov     rcx, rdi
0x140017bd8  call    UdfUnpinView
0x140017bdd  test    rsi, rsi
0x140017be0  jz      short loc_140017BF8
0x140017be2  mov     rdx, rsi; Entry
0x140017be5  lea     rcx, UdfScbDataLookasideList; Lookaside
0x140017bec  call    cs:__imp_ExFreeToPagedLookasideList
0x140017bf3  nop     dword ptr [rax+rax+00h]
0x140017bf8  mov     al, [rsp+268h+var_237]
0x140017bfc  jmp     loc_1400178D1
0x14001deb6  push    rbp
0x14001deb8  sub     rsp, 30h
0x14001debc  mov     rbp, rdx
0x14001debf  mov     rdx, rcx
0x14001dec2  mov     rcx, [rbp+40h]
0x14001dec6  call    UdfExceptionFilter
0x14001decb  nop
0x14001decc  add     rsp, 30h
0x14001ded0  pop     rbp
0x14001ded1  retn
0x14001ded3  push    rbp
0x14001ded5  sub     rsp, 30h
0x14001ded9  mov     rbp, rdx
0x14001dedc  mov     rdx, rcx
0x14001dedf  mov     rcx, [rbp+40h]
0x14001dee3  call    UdfExceptionFilter
0x14001dee8  nop
0x14001dee9  add     rsp, 30h
0x14001deed  pop     rbp
0x14001deee  retn
0x14001def0  push    rbp
0x14001def2  sub     rsp, 30h
0x14001def6  mov     rbp, rdx
0x14001def9  cmp     byte ptr [rbp+30h], 0
0x14001defd  jz      short loc_14001DF10
0x14001deff  lea     rdx, [rbp+0A0h]
0x14001df06  mov     rcx, [rbp+40h]
0x14001df0a  call    UdfCleanupCompoundDirContext
0x14001df0f  nop
0x14001df10  lea     rdx, [rbp+78h]
0x14001df14  mov     rcx, [rbp+40h]
0x14001df18  call    UdfUnpinView
0x14001df1d  mov     rdx, [rbp+58h]; Entry
0x14001df21  test    rdx, rdx
0x14001df24  jz      short loc_14001DF3A
0x14001df26  lea     rcx, UdfScbDataLookasideList; Lookaside
0x14001df2d  call    cs:__imp_ExFreeToPagedLookasideList
0x14001df34  nop     dword ptr [rax+rax+00h]
0x14001df39  nop
0x14001df3a  add     rsp, 30h
0x14001df3e  pop     rbp
0x14001df3f  retn
```
