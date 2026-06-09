# Tpm20Context::CreateInternalTpm20Request(Tpm20Context *,_TPM20RM_COMPLETION *,void (*)(_TPM20RM_COMPLETION *),void *,uint,void *,uint,Tpm20Request * *)

- ea: `0x1400034a8`
- end: `0x14000369e`
- name: `?CreateInternalTpm20Request@Tpm20Context@@SAJPEAV1@PEAU_TPM20RM_COMPLETION@@P6AX1@ZPEAXI3IPEAPEAVTpm20Request@@@Z`
- size: `502`
- prototype: `static int(struct Tpm20Context *, struct _TPM20RM_COMPLETION *, void (*)(struct _TPM20RM_COMPLETION *), void *, unsigned int, void *, unsigned int, struct Tpm20Request **)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140003380`
- `0x14001c7cc`
- `0x14001c944`

## callees

- `0x1400034a8`
- `0x1400036b0`
- `0x140003850`
- `0x140039740`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400035bb`
- `ntoskrnl!KeInitializeEvent` at `0x1400035bb`

## pseudocode

```c
__int64 __fastcall Tpm20Context::CreateInternalTpm20Request(
        struct Tpm20Context *a1,
        struct _KEVENT *a2,
        void (*a3)(struct _TPM20RM_COMPLETION *),
        char *a4,
        unsigned int a5,
        void *a6,
        unsigned int a7,
        struct Tpm20Request **a8)
{
  int v12; // edx
  signed int i; // edx
  __int64 v14; // rcx
  char *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // r10
  signed int v18; // r8d
  char *v19; // r11
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  signed int j; // edx
  __int64 v25; // rcx
  char *v26; // rax
  void *v27; // rax
  struct Tpm20Request *v28; // rax
  __int64 v30; // [rsp+70h] [rbp-58h] BYREF
  __int16 v31; // [rsp+78h] [rbp-50h]
  __int64 v32; // [rsp+80h] [rbp-48h]
  __int16 v33; // [rsp+88h] [rbp-40h]

  v32 = 0;
  v33 = 0;
  if ( a5 < 0xA || a7 < 0xA )
    return 3221225485LL;
  v12 = (int)a4;
  if ( a5 >= 2uLL )
  {
    for ( i = 0; (unsigned int)i < 2; ++i )
    {
      v14 = i;
      v15 = &a4[-i + 1];
      *((_BYTE *)&v32 + v14) = *v15;
    }
    v12 = (_DWORD)a4 + 2;
  }
  v16 = (unsigned int)(v12 - (_DWORD)a4);
  if ( (int)v16 + 4 < (unsigned int)v16 || (v17 = (unsigned int)v16, v16 + 4 > (unsigned __int64)a5) )
  {
    v19 = a4 + 3;
  }
  else
  {
    v18 = 0;
    v19 = a4 + 3;
    do
    {
      v20 = v18;
      v21 = v17 - v18++;
      *((_BYTE *)&v32 + v20 + 2) = v19[v21];
    }
    while ( (unsigned int)v18 < 4 );
    v12 += 4;
  }
  v22 = (unsigned int)(v12 - (_DWORD)a4);
  if ( (int)v22 + 4 >= (unsigned int)v22 )
  {
    v23 = (unsigned int)v22;
    if ( v22 + 4 <= (unsigned __int64)a5 )
    {
      for ( j = 0; (unsigned int)j < 4; ++j )
      {
        v25 = j;
        v26 = &v19[-j];
        *((_BYTE *)&v32 + v25 + 6) = v26[v23];
      }
    }
  }
  KeInitializeEvent(a2, NotificationEvent, 0);
  *(_QWORD *)&a2[1].Header.Lock = a3;
  v27 = AllocatorBase::operator new(0x120u);
  if ( !v27 )
    return 3221225626LL;
  v31 = v33;
  v30 = v32;
  v28 = (struct Tpm20Request *)((__int64 (__fastcall *)(void *, _QWORD, struct _KEVENT *, struct Tpm20Context *, int, _QWORD, _QWORD, int, char *, unsigned int, void *, unsigned int, _QWORD, __int64 *))Tpm20Request::Tpm20Request)(
                                 v27,
                                 0,
                                 a2,
                                 a1,
                                 -1,
                                 0,
                                 0,
                                 2,
                                 a4,
                                 a5,
                                 a6,
                                 a7,
                                 0,
                                 &v30);
  if ( !v28 )
    return 3221225626LL;
  *a8 = v28;
  return 0;
}

```

## disassembly

```asm
0x1400034a8  mov     r11, rsp
0x1400034ab  mov     [r11+8], rbx
0x1400034af  mov     [r11+18h], rbp
0x1400034b3  push    rsi
0x1400034b4  push    rdi
0x1400034b5  push    r12
0x1400034b7  push    r14
0x1400034b9  push    r15
0x1400034bb  sub     rsp, 0A0h
0x1400034c2  mov     rax, cs:__security_cookie
0x1400034c9  xor     rax, rsp
0x1400034cc  mov     [rsp+0C8h+var_38], rax
0x1400034d4  mov     edi, [rsp+0C8h+arg_20]
0x1400034db  xor     eax, eax
0x1400034dd  mov     r14, [rsp+0C8h+arg_38]
0x1400034e5  mov     rbx, r9
0x1400034e8  mov     [r11-48h], rax
0x1400034ec  mov     r15, r8
0x1400034ef  mov     [r11-40h], ax
0x1400034f4  mov     rbp, rdx
0x1400034f7  mov     r12, rcx
0x1400034fa  cmp     edi, 0Ah
0x1400034fd  jb      loc_14000366C
0x140003503  mov     esi, [rsp+0C8h+arg_30]
0x14000350a  cmp     esi, 0Ah
0x14000350d  jb      loc_14000366C
0x140003513  mov     rdx, rbx
0x140003516  cmp     rdi, 2
0x14000351a  jb      short loc_14000353C
0x14000351c  xor     edx, edx
0x14000351e  movsxd  rcx, edx
0x140003521  lea     rax, [r9+1]
0x140003525  sub     rax, rcx
0x140003528  inc     edx
0x14000352a  mov     al, [rax]
0x14000352c  mov     byte ptr [rsp+rcx+0C8h+var_48], al
0x140003533  cmp     edx, 2
0x140003536  jb      short loc_14000351E
0x140003538  lea     rdx, [r9+2]
0x14000353c  mov     ecx, edx
0x14000353e  sub     ecx, ebx
0x140003540  lea     eax, [rcx+4]
0x140003543  cmp     eax, ecx
0x140003545  jb      short loc_14000357D
0x140003547  lea     rax, [rcx+4]
0x14000354b  mov     r10d, ecx
0x14000354e  cmp     rax, rdi
0x140003551  ja      short loc_14000357D
0x140003553  xor     r8d, r8d
0x140003556  lea     r11, [r9+3]
0x14000355a  movsxd  rcx, r8d
0x14000355d  mov     rax, r10
0x140003560  sub     rax, rcx
0x140003563  inc     r8d
0x140003566  mov     al, [rax+r11]
0x14000356a  mov     byte ptr [rsp+rcx+0C8h+var_48+2], al
0x140003571  cmp     r8d, 4
0x140003575  jb      short loc_14000355A
0x140003577  add     rdx, 4
0x14000357b  jmp     short loc_140003581
0x14000357d  lea     r11, [r9+3]
0x140003581  sub     edx, ebx
0x140003583  lea     eax, [rdx+4]
0x140003586  cmp     eax, edx
0x140003588  jb      short loc_1400035B3
0x14000358a  lea     rax, [rdx+4]
0x14000358e  mov     r8d, edx
0x140003591  cmp     rax, rdi
0x140003594  ja      short loc_1400035B3
0x140003596  xor     edx, edx
0x140003598  movsxd  rcx, edx
0x14000359b  mov     rax, r11
0x14000359e  sub     rax, rcx
0x1400035a1  inc     edx
0x1400035a3  mov     al, [rax+r8]
0x1400035a7  mov     byte ptr [rsp+rcx+0C8h+var_48+6], al
0x1400035ae  cmp     edx, 4
0x1400035b1  jb      short loc_140003598
0x1400035b3  xor     r8d, r8d; State
0x1400035b6  xor     edx, edx; Type
0x1400035b8  mov     rcx, rbp; Event
0x1400035bb  call    cs:__imp_KeInitializeEvent
0x1400035c2  nop     dword ptr [rax+rax+00h]
0x1400035c7  mov     ecx, 120h; Size
0x1400035cc  mov     [rbp+18h], r15
0x1400035d0  call    ??2AllocatorBase@@SAPEAX_K@Z; AllocatorBase::operator new(unsigned __int64)
0x1400035d5  test    rax, rax
0x1400035d8  jz      loc_140003665
0x1400035de  movzx   ecx, [rsp+0C8h+var_40]
0x1400035e6  mov     r9, r12
0x1400035e9  movsd   xmm0, [rsp+0C8h+var_48]
0x1400035f2  mov     r8, rbp
0x1400035f5  mov     [rsp+0C8h+var_50], cx
0x1400035fa  xor     edx, edx
0x1400035fc  lea     rcx, [rsp+0C8h+var_58]
0x140003601  movsd   [rsp+0C8h+var_58], xmm0
0x140003607  mov     [rsp+0C8h+var_60], rcx
0x14000360c  mov     rcx, [rsp+0C8h+arg_28]
0x140003614  mov     [rsp+0C8h+var_68], 0
0x14000361d  mov     [rsp+0C8h+var_70], esi
0x140003621  mov     [rsp+0C8h+var_78], rcx
0x140003626  mov     rcx, rax
0x140003629  mov     [rsp+0C8h+var_80], edi
0x14000362d  mov     [rsp+0C8h+var_88], rbx
0x140003632  mov     [rsp+0C8h+var_90], 2
0x14000363a  mov     [rsp+0C8h+var_98], 0
0x140003643  mov     [rsp+0C8h+var_A0], 0
0x14000364c  mov     [rsp+0C8h+var_A8], 0FFFFFFFFh
0x140003654  call    ??0Tpm20Request@@AEAA@PEAUWDFREQUEST__@@PEAU_TPM20RM_COMPLETION@@PEAVTpm20Context@@IPEBG3W4_USER_TYPE@@PEAXI5I5U_TPM20_CMD_HEADER@@@Z; Tpm20Request::Tpm20Request(WDFREQUEST__ *,_TPM20RM_COMPLETION *,Tpm20Context *,uint,ushort const *,ushort const *,_USER_TYPE,void *,uint,void *,uint,void *,_TPM20_CMD_HEADER)
0x140003659  test    rax, rax
0x14000365c  jz      short loc_140003665
0x14000365e  mov     [r14], rax
0x140003661  xor     eax, eax
0x140003663  jmp     short loc_140003671
0x140003665  mov     eax, 0C000009Ah
0x14000366a  jmp     short loc_140003671
0x14000366c  mov     eax, 0C000000Dh
0x140003671  mov     rcx, [rsp+0C8h+var_38]
0x140003679  xor     rcx, rsp; StackCookie
0x14000367c  call    __security_check_cookie
0x140003681  lea     r11, [rsp+0C8h+var_28]
0x140003689  mov     rbx, [r11+30h]
0x14000368d  mov     rbp, [r11+40h]
0x140003691  mov     rsp, r11
0x140003694  pop     r15
0x140003696  pop     r14
0x140003698  pop     r12
0x14000369a  pop     rdi
0x14000369b  pop     rsi
0x14000369c  retn
```
