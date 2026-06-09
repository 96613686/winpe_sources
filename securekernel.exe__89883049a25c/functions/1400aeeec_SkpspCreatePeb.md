# SkpspCreatePeb

- ea: `0x1400aeeec`
- end: `0x1400af1c3`
- name: `SkpspCreatePeb`
- size: `727`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x14002b5f4`

## callees

- `0x14001e53c`
- `0x14002ba08`
- `0x14005af28`
- `0x14005bbe8`
- `0x1400aeeec`
- `0x1400af1cc`
- `0x1400af790`
- `0x1400f3620`
- `0x1400f9a80`
- `0x1400fc554`
- `0x1400fc62c`
- `0x1400fc664`
- `0x1400fc6a0`
- `0x1400fc6dc`

## pseudocode

```c
__int64 __fastcall SkpspCreatePeb(__int64 a1, unsigned int *a2)
{
  __int64 result; // rax
  int ApiSetAndNlsSectionInformation; // ebx
  int v6; // eax
  void *PebOrTeb; // rax
  _BYTE Src[3]; // [rsp+30h] [rbp-7F8h] BYREF
  char UCharFromUser; // [rsp+33h] [rbp-7F5h]
  __int64 ULong64FromUser; // [rsp+38h] [rbp-7F0h]
  __int64 v11; // [rsp+40h] [rbp-7E8h]
  PVOID v12; // [rsp+50h] [rbp-7D8h] BYREF
  int v13; // [rsp+E8h] [rbp-740h]
  int v14; // [rsp+ECh] [rbp-73Ch]
  __int64 v15; // [rsp+F0h] [rbp-738h]
  __int64 v16; // [rsp+F8h] [rbp-730h]
  __int64 v17; // [rsp+100h] [rbp-728h]
  __int64 v18; // [rsp+108h] [rbp-720h]
  __int64 v19; // [rsp+110h] [rbp-718h]
  int v20; // [rsp+11Ch] [rbp-70Ch]
  __int64 v21; // [rsp+120h] [rbp-708h]
  int ULongFromUser; // [rsp+148h] [rbp-6E0h]
  int v23; // [rsp+14Ch] [rbp-6DCh]
  __int16 UShortFromUser; // [rsp+150h] [rbp-6D8h]
  __int16 v25; // [rsp+152h] [rbp-6D6h]
  int v26; // [rsp+154h] [rbp-6D4h]
  int v27; // [rsp+158h] [rbp-6D0h]
  int v28; // [rsp+15Ch] [rbp-6CCh]
  int v29; // [rsp+160h] [rbp-6C8h]
  int v30; // [rsp+2F0h] [rbp-538h]
  __int64 v31; // [rsp+348h] [rbp-4E0h]

  memset_0(Src, 0, 0x7D0u);
  result = SkmmInjectTemporaryMapping(a2, 4096);
  if ( (int)result >= 0 )
  {
    memset_0(Src, 0, 0x7D0u);
    v11 = *(_QWORD *)(a1 + 176);
    v13 = SkeNumberProcessors;
    ApiSetAndNlsSectionInformation = SkpspGetApiSetAndNlsSectionInformation(Src);
    if ( ApiSetAndNlsSectionInformation >= 0 )
    {
      v6 = SkpspCreateSecureProcessParameters(a1, &v12);
      ApiSetAndNlsSectionInformation = v6;
      if ( v6 >= 0 )
      {
        UCharFromUser = RtlReadUCharFromUser((char *)a2 + 3);
        ULongFromUser = RtlReadULongFromUser(a2 + 70);
        v23 = RtlReadULongFromUser(a2 + 71);
        UShortFromUser = RtlReadUShortFromUser(a2 + 72);
        v25 = RtlReadUShortFromUser((char *)a2 + 290);
        v26 = RtlReadULongFromUser(a2 + 73);
        v27 = RtlReadULongFromUser(a2 + 74);
        v28 = RtlReadULongFromUser(a2 + 75);
        v29 = RtlReadULongFromUser(a2 + 76);
        v30 = RtlReadULongFromUser(a2 + 176);
        Src[0] = RtlReadUCharFromUser(a2);
        ULong64FromUser = RtlReadULong64FromUser(a2 + 2);
        v14 = NtGlobalFlag | RtlReadULongFromUser(a2 + 47);
        v16 = RtlReadULong64FromUser(a2 + 50);
        v17 = RtlReadULong64FromUser(a2 + 52);
        v18 = RtlReadULong64FromUser(a2 + 54);
        v19 = RtlReadULong64FromUser(a2 + 56);
        v20 = RtlReadULongFromUser(a2 + 59);
        v21 = RtlReadULong64FromUser(a2 + 60);
        v31 = RtlReadULong64FromUser(a2 + 198);
        v15 = RtlReadULong64FromUser(a2 + 48);
        v14 &= 0xFDFFFEFF;
        UCharFromUser = UCharFromUser & 0xFC | 2;
        PebOrTeb = (void *)SkmiAllocatePebOrTeb(2000);
        *(_QWORD *)(a1 + 160) = PebOrTeb;
        if ( PebOrTeb )
        {
          RtlCopyToUser(PebOrTeb, Src, 0x7D0u);
          ApiSetAndNlsSectionInformation = 0;
        }
        else
        {
          ApiSetAndNlsSectionInformation = -1073741801;
        }
      }
      else
      {
        DbgPrint("ProcessParams creation failed with error 0x%x\n", v6);
      }
    }
    SkmmReleaseTemporaryView(a2, 4096);
    return (unsigned int)ApiSetAndNlsSectionInformation;
  }
  return result;
}

```

## disassembly

```asm
0x1400aeeec  mov     [rsp+arg_10], rbx
0x1400aeef1  push    rsi
0x1400aeef2  push    rdi
0x1400aeef3  push    r14
0x1400aeef5  sub     rsp, 810h
0x1400aeefc  mov     rax, cs:__security_cookie
0x1400aef03  xor     rax, rsp
0x1400aef06  mov     [rsp+828h+var_28], rax
0x1400aef0e  mov     rdi, rdx
0x1400aef11  mov     rsi, rcx
0x1400aef14  mov     [rsp+828h+var_808], rdx
0x1400aef19  mov     r14d, 7D0h
0x1400aef1f  mov     r8d, r14d; Size
0x1400aef22  xor     edx, edx; Val
0x1400aef24  lea     rcx, [rsp+828h+Src]; void *
0x1400aef29  call    memset_0
0x1400aef2e  mov     edx, 1000h
0x1400aef33  mov     rcx, rdi
0x1400aef36  call    SkmmInjectTemporaryMapping
0x1400aef3b  test    eax, eax
0x1400aef3d  js      loc_1400AF19E
0x1400aef43  mov     r8d, r14d; Size
0x1400aef46  xor     edx, edx; Val
0x1400aef48  lea     rcx, [rsp+828h+Src]; void *
0x1400aef4d  call    memset_0
0x1400aef52  mov     rax, [rsi+0B0h]
0x1400aef59  mov     [rsp+828h+var_7E8], rax
0x1400aef5e  mov     eax, cs:SkeNumberProcessors
0x1400aef64  mov     [rsp+828h+var_740], eax
0x1400aef6b  lea     rcx, [rsp+828h+Src]
0x1400aef70  call    SkpspGetApiSetAndNlsSectionInformation
0x1400aef75  mov     ebx, eax
0x1400aef77  test    eax, eax
0x1400aef79  js      loc_1400AF18F
0x1400aef7f  mov     r8, rdi
0x1400aef82  lea     rdx, [rsp+828h+var_7D8]
0x1400aef87  mov     rcx, rsi
0x1400aef8a  call    SkpspCreateSecureProcessParameters
0x1400aef8f  mov     ebx, eax
0x1400aef91  test    eax, eax
0x1400aef93  jns     short loc_1400AEFA8
0x1400aef95  mov     edx, eax
0x1400aef97  lea     rcx, aProcessparamsC; "ProcessParams creation failed with erro"...
0x1400aef9e  call    DbgPrint
0x1400aefa3  jmp     loc_1400AF18F
0x1400aefa8  lea     rcx, [rdi+3]
0x1400aefac  call    RtlReadUCharFromUser
0x1400aefb1  mov     [rsp+828h+var_7F5], al
0x1400aefb5  lea     rcx, [rdi+118h]
0x1400aefbc  call    RtlReadULongFromUser
0x1400aefc1  mov     [rsp+828h+var_6E0], eax
0x1400aefc8  lea     rcx, [rdi+11Ch]
0x1400aefcf  call    RtlReadULongFromUser
0x1400aefd4  mov     [rsp+828h+var_6DC], eax
0x1400aefdb  lea     rcx, [rdi+120h]
0x1400aefe2  call    RtlReadUShortFromUser
0x1400aefe7  mov     [rsp+828h+var_6D8], ax
0x1400aefef  lea     rcx, [rdi+122h]
0x1400aeff6  call    RtlReadUShortFromUser
0x1400aeffb  mov     [rsp+828h+var_6D6], ax
0x1400af003  lea     rcx, [rdi+124h]
0x1400af00a  call    RtlReadULongFromUser
0x1400af00f  mov     [rsp+828h+var_6D4], eax
0x1400af016  lea     rcx, [rdi+128h]
0x1400af01d  call    RtlReadULongFromUser
0x1400af022  mov     [rsp+828h+var_6D0], eax
0x1400af029  lea     rcx, [rdi+12Ch]
0x1400af030  call    RtlReadULongFromUser
0x1400af035  mov     [rsp+828h+var_6CC], eax
0x1400af03c  lea     rcx, [rdi+130h]
0x1400af043  call    RtlReadULongFromUser
0x1400af048  mov     [rsp+828h+var_6C8], eax
0x1400af04f  lea     rcx, [rdi+2C0h]
0x1400af056  call    RtlReadULongFromUser
0x1400af05b  mov     [rsp+828h+var_538], eax
0x1400af062  mov     rcx, rdi
0x1400af065  call    RtlReadUCharFromUser
0x1400af06a  mov     [rsp+828h+Src], al
0x1400af06e  lea     rcx, [rdi+8]
0x1400af072  call    RtlReadULong64FromUser
0x1400af077  mov     [rsp+828h+var_7F0], rax
0x1400af07c  lea     rcx, [rdi+0BCh]
0x1400af083  call    RtlReadULongFromUser
0x1400af088  or      eax, cs:NtGlobalFlag
0x1400af08e  mov     [rsp+828h+var_73C], eax
0x1400af095  lea     rcx, [rdi+0C8h]
0x1400af09c  call    RtlReadULong64FromUser
0x1400af0a1  mov     [rsp+828h+var_730], rax
0x1400af0a9  lea     rcx, [rdi+0D0h]
0x1400af0b0  call    RtlReadULong64FromUser
0x1400af0b5  mov     [rsp+828h+var_728], rax
0x1400af0bd  lea     rcx, [rdi+0D8h]
0x1400af0c4  call    RtlReadULong64FromUser
0x1400af0c9  mov     [rsp+828h+var_720], rax
0x1400af0d1  lea     rcx, [rdi+0E0h]
0x1400af0d8  call    RtlReadULong64FromUser
0x1400af0dd  mov     [rsp+828h+var_718], rax
0x1400af0e5  lea     rcx, [rdi+0ECh]
0x1400af0ec  call    RtlReadULongFromUser
0x1400af0f1  mov     [rsp+828h+var_70C], eax
0x1400af0f8  lea     rcx, [rdi+0F0h]
0x1400af0ff  call    RtlReadULong64FromUser
0x1400af104  mov     [rsp+828h+var_708], rax
0x1400af10c  lea     rcx, [rdi+318h]
0x1400af113  call    RtlReadULong64FromUser
0x1400af118  mov     [rsp+828h+var_4E0], rax
0x1400af120  lea     rcx, [rdi+0C0h]
0x1400af127  call    RtlReadULong64FromUser
0x1400af12c  mov     [rsp+828h+var_738], rax
0x1400af134  mov     al, [rsp+828h+var_7F5]
0x1400af138  and     al, 0FEh
0x1400af13a  mov     [rsp+828h+var_7F5], al
0x1400af13e  and     [rsp+828h+var_73C], 0FDFFFEFFh
0x1400af149  or      al, 2
0x1400af14b  mov     [rsp+828h+var_7F5], al
0x1400af14f  mov     rcx, r14
0x1400af152  call    SkmiAllocatePebOrTeb
0x1400af157  mov     [rsi+0A0h], rax
0x1400af15e  test    rax, rax
0x1400af161  jnz     short loc_1400AF16A
0x1400af163  mov     ebx, 0C0000017h
0x1400af168  jmp     short loc_1400AF18F
0x1400af16a  mov     r8, r14; Size
0x1400af16d  lea     rdx, [rsp+828h+Src]; Src
0x1400af172  mov     rcx, rax; void *
0x1400af175  call    RtlCopyToUser
0x1400af17a  nop
0x1400af17b  xor     ebx, ebx
0x1400af17d  jmp     short loc_1400AF18F
0x1400af17f  mov     ebx, eax
0x1400af181  mov     rdi, [rsp+828h+var_808]
0x1400af186  jmp     short loc_1400AF18F
0x1400af188  mov     ebx, eax
0x1400af18a  mov     rdi, [rsp+828h+var_808]
0x1400af18f  mov     edx, 1000h
0x1400af194  mov     rcx, rdi
0x1400af197  call    SkmmReleaseTemporaryView
0x1400af19c  mov     eax, ebx
0x1400af19e  mov     rcx, [rsp+828h+var_28]
0x1400af1a6  xor     rcx, rsp; StackCookie
0x1400af1a9  call    __security_check_cookie
0x1400af1ae  mov     rbx, [rsp+828h+arg_10]
0x1400af1b6  add     rsp, 810h
0x1400af1bd  pop     r14
0x1400af1bf  pop     rdi
0x1400af1c0  pop     rsi
0x1400af1c1  retn
```
