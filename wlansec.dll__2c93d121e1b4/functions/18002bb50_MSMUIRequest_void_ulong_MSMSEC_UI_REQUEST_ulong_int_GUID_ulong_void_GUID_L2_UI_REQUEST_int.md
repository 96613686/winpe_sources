# MSMUIRequest(void *,ulong,MSMSEC_UI_REQUEST *,ulong,int,_GUID *,ulong (*)(void *,_GUID *,_L2_UI_REQUEST *,int))

- ea: `0x18002bb50`
- end: `0x18002be2b`
- name: `?MSMUIRequest@@YAKPEAXKPEAUMSMSEC_UI_REQUEST@@KHPEAU_GUID@@P6AK02PEAU_L2_UI_REQUEST@@H@Z@Z`
- size: `731`
- prototype: `unsigned int(void *, unsigned int, struct MSMSEC_UI_REQUEST *, unsigned int, int, struct _GUID *, unsigned int (*)(void *, struct _GUID *, struct _L2_UI_REQUEST *, int))`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x18002b770`
- `0x1800363c0`

## callees

- `0x1800063b0`
- `0x18000892c`
- `0x180008998`
- `0x18000bde0`
- `0x18000c730`
- `0x18002bb50`
- `0x180036f38`
- `0x180043a30`
- `0x180044554`
- `0x18005639c`
- `0x180096010`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18002bbce`
- `RPCRT4!UuidCreate` at `0x18002bbce`

## pseudocode

```c
__int64 __fastcall MSMUIRequest(
        void *a1,
        unsigned int a2,
        struct MSMSEC_UI_REQUEST *a3,
        int a4,
        unsigned int a5,
        struct _GUID *a6,
        unsigned int (*a7)(void *, struct _GUID *, struct _L2_UI_REQUEST *, int))
{
  size_t v9; // rsi
  SIZE_T v11; // rcx
  unsigned int v12; // ebx
  PVOID *v13; // rcx
  unsigned int MSMSecMemory; // eax
  int v16; // ecx
  const wchar_t *v17; // r9
  unsigned int v18; // eax
  UUID Uuid; // [rsp+38h] [rbp-60h] BYREF

  Uuid = 0;
  v9 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 97, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids);
  UuidCreate(&Uuid);
  v11 = (unsigned int)(v9 + 664);
  if ( (unsigned int)v11 >= (unsigned int)v9 )
  {
    MSMSecMemory = AllocateMSMSecMemory(v11);
    v12 = MSMSecMemory;
    if ( MSMSecMemory )
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_8;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 99, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids, MSMSecMemory);
    }
    else
    {
      MEMORY[0x30] = a4;
      MEMORY[0x34] = *a6;
      MEMORY[0x44] = v9 + 576;
      MEMORY[0x284] = 2;
      MEMORY[0x28C] = v9;
      memcpy_0((void *)0x298, a3, v9);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
      {
        switch ( *(_DWORD *)a3 )
        {
          case 1:
            v17 = L"Key";
            break;
          case 2:
            v17 = L"PSK";
            break;
          case 4:
            v17 = L"802.1x";
            break;
          default:
            v17 = L"Invalid";
            break;
        }
        WPP_SF_SL(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          100,
          (unsigned int)&WPP_b56916f94f50376d7382066de30fa1b3_Traceguids,
          (_DWORD)v17,
          *(_DWORD *)a3);
      }
      if ( (byte_1800AED45 & 1) != 0 )
        McTemplateU0qjq_EventWriteTransfer(v16, (unsigned int)MsmSecSendUIRequest, a4, (_DWORD)a6, *(_DWORD *)a3);
      v18 = ((__int64 (__fastcall *)(void *, UUID *, _QWORD, _QWORD))a7)(a1, &Uuid, 0, a5);
      v12 = v18;
      if ( v18 )
      {
        v13 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_8;
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 101, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids, v18);
      }
    }
    v13 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_8;
  }
  v12 = 534;
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      98,
      &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids,
      (unsigned int)v9);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_8:
  if ( v13 != &WPP_GLOBAL_Control && (*((_DWORD *)v13 + 17) & 0x100) != 0 )
    WPP_SF_d(v13[7], 102, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x18002bb50  push    rbx
0x18002bb52  push    rbp
0x18002bb53  push    rsi
0x18002bb54  push    rdi
0x18002bb55  push    r12
0x18002bb57  push    r13
0x18002bb59  push    r14
0x18002bb5b  push    r15
0x18002bb5d  sub     rsp, 58h
0x18002bb61  mov     rax, cs:__security_cookie
0x18002bb68  xor     rax, rsp
0x18002bb6b  mov     [rsp+98h+var_50], rax
0x18002bb70  mov     r15, [rsp+98h+arg_28]
0x18002bb78  xor     edi, edi
0x18002bb7a  mov     r13, [rsp+98h+arg_30]
0x18002bb82  xorps   xmm0, xmm0
0x18002bb85  mov     [rsp+98h+var_68], rdi
0x18002bb8a  mov     ebp, r9d
0x18002bb8d  movups  xmmword ptr [rsp+98h+Uuid.Data1], xmm0
0x18002bb92  mov     r14, r8
0x18002bb95  mov     esi, edx
0x18002bb97  mov     r12, rcx
0x18002bb9a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bba1  lea     rax, WPP_GLOBAL_Control
0x18002bba8  cmp     rcx, rax
0x18002bbab  jz      short loc_18002BBC9
0x18002bbad  test    dword ptr [rcx+44h], 100h
0x18002bbb4  jz      short loc_18002BBC9
0x18002bbb6  mov     rcx, [rcx+38h]
0x18002bbba  lea     edx, [rdi+61h]
0x18002bbbd  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x18002bbc4  call    WPP_SF_
0x18002bbc9  lea     rcx, [rsp+98h+Uuid]; Uuid
0x18002bbce  call    cs:__imp_UuidCreate
0x18002bbd5  nop     dword ptr [rax+rax+00h]
0x18002bbda  lea     ecx, [rsi+298h]; dwBytes
0x18002bbe0  cmp     ecx, esi
0x18002bbe2  jnb     loc_18002BCAA
0x18002bbe8  mov     ebx, 216h
0x18002bbed  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bbf4  lea     rax, WPP_GLOBAL_Control
0x18002bbfb  cmp     rcx, rax
0x18002bbfe  jz      short loc_18002BC25
0x18002bc00  test    byte ptr [rcx+44h], 1
0x18002bc04  jz      short loc_18002BC25
0x18002bc06  mov     rcx, [rcx+38h]
0x18002bc0a  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x18002bc11  mov     edx, 62h ; 'b'
0x18002bc16  mov     r9d, esi
0x18002bc19  call    WPP_SF_d
0x18002bc1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bc25  lea     rsi, WPP_GLOBAL_Control
0x18002bc2c  test    rdi, rdi
0x18002bc2f  jz      short loc_18002BC63
0x18002bc31  cmp     rcx, rsi
0x18002bc34  jz      short loc_18002BC54
0x18002bc36  test    byte ptr [rcx+1Ch], 10h
0x18002bc3a  jz      short loc_18002BC54
0x18002bc3c  mov     rcx, [rcx+10h]
0x18002bc40  lea     r8, WPP_13d7b2876eef3b3479d595a943243812_Traceguids
0x18002bc47  mov     edx, 0Ch
0x18002bc4c  mov     r9, rdi
0x18002bc4f  call    WPP_SF_q
0x18002bc54  mov     rcx, rdi
0x18002bc57  call    FreeWLMemory
0x18002bc5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bc63  cmp     rcx, rsi
0x18002bc66  jz      short loc_18002BC89
0x18002bc68  test    dword ptr [rcx+44h], 100h
0x18002bc6f  jz      short loc_18002BC89
0x18002bc71  mov     rcx, [rcx+38h]
0x18002bc75  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x18002bc7c  mov     edx, 66h ; 'f'
0x18002bc81  mov     r9d, ebx
0x18002bc84  call    WPP_SF_d
0x18002bc89  mov     eax, ebx
0x18002bc8b  mov     rcx, [rsp+98h+var_50]
0x18002bc90  xor     rcx, rsp; StackCookie
0x18002bc93  call    __security_check_cookie
0x18002bc98  add     rsp, 58h
0x18002bc9c  pop     r15
0x18002bc9e  pop     r14
0x18002bca0  pop     r13
0x18002bca2  pop     r12
0x18002bca4  pop     rdi
0x18002bca5  pop     rsi
0x18002bca6  pop     rbp
0x18002bca7  pop     rbx
0x18002bca8  retn
0x18002bcaa  lea     rdx, [rsp+98h+var_68]
0x18002bcaf  call    AllocateMSMSecMemory
0x18002bcb4  mov     ebx, eax
0x18002bcb6  test    eax, eax
0x18002bcb8  jz      short loc_18002BD06
0x18002bcba  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bcc1  lea     rsi, WPP_GLOBAL_Control
0x18002bcc8  cmp     rcx, rsi
0x18002bccb  jz      short loc_18002BCFC
0x18002bccd  test    byte ptr [rcx+44h], 1
0x18002bcd1  jz      short loc_18002BCFC
0x18002bcd3  mov     rcx, [rcx+38h]
0x18002bcd7  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x18002bcde  mov     edx, 63h ; 'c'
0x18002bce3  mov     r9d, eax
0x18002bce6  call    WPP_SF_d
0x18002bceb  mov     rdi, [rsp+98h+var_68]
0x18002bcf0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bcf7  jmp     loc_18002BC2C
0x18002bcfc  mov     rdi, [rsp+98h+var_68]
0x18002bd01  jmp     loc_18002BC2C
0x18002bd06  mov     rdi, [rsp+98h+var_68]
0x18002bd0b  lea     eax, [rsi+240h]
0x18002bd11  mov     r8, rsi; Size
0x18002bd14  mov     rdx, r14; Src
0x18002bd17  mov     [rdi+30h], ebp
0x18002bd1a  lea     rcx, [rdi+298h]; void *
0x18002bd21  movups  xmm0, xmmword ptr [r15]
0x18002bd25  movdqu  xmmword ptr [rdi+34h], xmm0
0x18002bd2a  mov     [rdi+44h], eax
0x18002bd2d  mov     dword ptr [rdi+284h], 2
0x18002bd37  mov     [rdi+28Ch], esi
0x18002bd3d  call    memcpy_0
0x18002bd42  mov     r10, cs:WPP_GLOBAL_Control
0x18002bd49  lea     rsi, WPP_GLOBAL_Control
0x18002bd50  cmp     r10, rsi
0x18002bd53  jz      short loc_18002BDAD
0x18002bd55  test    byte ptr [r10+44h], 2
0x18002bd5a  jz      short loc_18002BDAD
0x18002bd5c  mov     r8d, [r14]
0x18002bd5f  mov     ecx, r8d
0x18002bd62  sub     ecx, 1
0x18002bd65  jz      short loc_18002BD8C
0x18002bd67  sub     ecx, 1
0x18002bd6a  jz      short loc_18002BD83
0x18002bd6c  cmp     ecx, 2
0x18002bd6f  jz      short loc_18002BD7A
0x18002bd71  lea     r9, aInvalid_0; "Invalid"
0x18002bd78  jmp     short loc_18002BD93
0x18002bd7a  lea     r9, a8021x; "802.1x"
0x18002bd81  jmp     short loc_18002BD93
0x18002bd83  lea     r9, aPsk; "PSK"
0x18002bd8a  jmp     short loc_18002BD93
0x18002bd8c  lea     r9, aKey; "Key"
0x18002bd93  mov     rcx, [r10+38h]
0x18002bd97  mov     edx, 64h ; 'd'
0x18002bd9c  mov     [rsp+98h+var_78], r8d
0x18002bda1  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x18002bda8  call    WPP_SF_SL
0x18002bdad  test    cs:byte_1800AED45, 1
0x18002bdb4  jz      short loc_18002BDCF
0x18002bdb6  mov     edx, [r14]
0x18002bdb9  mov     r9, r15
0x18002bdbc  mov     [rsp+98h+var_78], edx
0x18002bdc0  mov     r8d, ebp
0x18002bdc3  lea     rdx, MsmSecSendUIRequest
0x18002bdca  call    McTemplateU0qjq_EventWriteTransfer
0x18002bdcf  mov     r9d, [rsp+98h+arg_20]
0x18002bdd7  lea     rdx, [rsp+98h+Uuid]
0x18002bddc  mov     r8, rdi
0x18002bddf  mov     rcx, r12
0x18002bde2  mov     rax, r13
0x18002bde5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bdea  mov     ebx, eax
0x18002bdec  test    eax, eax
0x18002bdee  jz      loc_18002BCF0
0x18002bdf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bdfb  cmp     rcx, rsi
0x18002bdfe  jz      loc_18002BC2C
0x18002be04  test    byte ptr [rcx+44h], 1
0x18002be08  jz      loc_18002BC2C
0x18002be0e  mov     rcx, [rcx+38h]
0x18002be12  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x18002be19  mov     edx, 65h ; 'e'
0x18002be1e  mov     r9d, eax
0x18002be21  call    WPP_SF_d
0x18002be26  jmp     loc_18002BCF0
```
