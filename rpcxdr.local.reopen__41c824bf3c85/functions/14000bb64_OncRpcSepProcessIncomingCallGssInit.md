# OncRpcSepProcessIncomingCallGssInit

- ea: `0x14000bb64`
- end: `0x14000bf7f`
- name: `OncRpcSepProcessIncomingCallGssInit`
- size: `1051`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x140009c14`

## callees

- `0x1400020c0`
- `0x140002170`
- `0x1400021b0`
- `0x140005830`
- `0x140006720`
- `0x140009540`
- `0x14000af44`
- `0x14000b140`
- `0x14000b340`
- `0x14000bb64`
- `0x14000c470`
- `0x14000c56c`
- `0x14000c7f4`
- `0x140012950`

## pseudocode

```c
__int64 __fastcall OncRpcSepProcessIncomingCallGssInit(__int64 a1, _DWORD *a2)
{
  bool v2; // zf
  char v5; // r14
  int v6; // eax
  __int64 Timer_high; // rdx
  int v8; // r8d
  int UserNameFromContext; // edi
  __int64 v10; // rbx
  __int16 v11; // ax
  struct _SecHandle *v12; // r8
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  __int64 v16; // [rsp+90h] [rbp+8h] BYREF

  v2 = *(_DWORD *)(a1 + 312) == 2;
  v16 = 0;
  if ( !v2 )
  {
    v5 = 0;
    UserNameFromContext = NfsMemMgrStructureAllocateByHandle(qword_14001AA00, a2, &v16);
    if ( UserNameFromContext < 0 )
    {
LABEL_6:
      v10 = v16;
      goto LABEL_47;
    }
    v10 = v16;
    NfsStandardHeaderReferenceNoType(v16);
    v12 = 0;
    goto LABEL_23;
  }
  v5 = 1;
  v6 = OncRpcSepInboundQueryAndRefGssCtx(&v16, *(unsigned int *)(a1 + 328));
  UserNameFromContext = v6;
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (Timer_high & 0x40) != 0 )
        WPP_SF_Dd(
          WPP_GLOBAL_Control->AttachedDevice,
          34,
          WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids,
          *(unsigned int *)(a1 + 328),
          v6);
    }
    goto LABEL_6;
  }
  v11 = *(_WORD *)(a1 + 220);
  v10 = v16;
  if ( v11 == 2 )
  {
    if ( *(_WORD *)(v16 + 132) != 2 || *(_DWORD *)(a1 + 224) != *(_DWORD *)(v16 + 136) )
      goto LABEL_16;
  }
  else if ( v11 != 23
         || *(_WORD *)(v16 + 132) != 23
         || *(_QWORD *)(a1 + 228) != *(_QWORD *)(v16 + 140)
         || *(_QWORD *)(a1 + 236) != *(_QWORD *)(v16 + 148) )
  {
    goto LABEL_16;
  }
  if ( _InterlockedCompareExchange((volatile signed __int32 *)(v16 + 68), 3, 1) != 1 )
  {
LABEL_16:
    NfsStandardHeaderDereferenceNoType(v10);
    v10 = 0;
    UserNameFromContext = -1073741790;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
      goto LABEL_47;
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids, 3221225506LL);
  }
  if ( UserNameFromContext < 0 )
    goto LABEL_47;
  v12 = (struct _SecHandle *)(v10 + 88);
LABEL_23:
  UserNameFromContext = OncRpcSepServerEstablishContext(
                          &phCredential,
                          a2,
                          v12,
                          *(_QWORD *)(a1 + 352),
                          *(_DWORD *)(a1 + 344),
                          (PCtxtHandle)(v10 + 88),
                          (_QWORD *)(a1 + 1016),
                          (_DWORD *)(a1 + 1024),
                          (PTimeStamp)(v10 + 104));
  if ( UserNameFromContext >= 0 )
  {
    *(_DWORD *)(v10 + 112) |= 1u;
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
  {
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      36,
      WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids,
      *(unsigned int *)(a1 + 328),
      UserNameFromContext);
  }
  if ( *a2 == 1 )
  {
    ++*(_DWORD *)(v10 + 72);
    OncRpcCopyAddress(v10 + 132, a1 + 220);
    *(_DWORD *)(v10 + 68) = 1;
    goto LABEL_41;
  }
  if ( *a2 )
  {
    *(_DWORD *)(v10 + 68) = 4;
LABEL_41:
    if ( UserNameFromContext < 0 )
      goto LABEL_47;
    goto LABEL_42;
  }
  *(_DWORD *)(v10 + 68) = 2;
  *(_DWORD *)(v10 + 72) = -1;
  OncRpcCopyAddress(v10 + 132, a1 + 220);
  UserNameFromContext = OncRpcSepQueryUserNameFromContext(v10, a2);
  if ( UserNameFromContext < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
      goto LABEL_47;
    v14 = 37;
    goto LABEL_35;
  }
  UserNameFromContext = OncRpcSepQuerySizesFromContext(v10, a2);
  if ( UserNameFromContext < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
      goto LABEL_47;
    v14 = 38;
LABEL_35:
    WPP_SF_Dd(
      v13->AttachedDevice,
      v14,
      WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids,
      *(unsigned int *)(a1 + 328),
      UserNameFromContext);
    goto LABEL_47;
  }
LABEL_42:
  v2 = *a2 == 0;
  *(_DWORD *)(a1 + 448) = 64;
  if ( v2 )
  {
    LODWORD(v16) = 0x40000000;
    *(_QWORD *)(a1 + 1072) = a1 + 376;
    *(_DWORD *)(a1 + 1080) = 64;
    UserNameFromContext = OncRpcSeMakeSignature(
                            (struct _SecHandle *)(v10 + 88),
                            a2,
                            0,
                            &v16,
                            4u,
                            (void *)(a1 + 376),
                            0x40u,
                            (unsigned int *)(a1 + 1080));
    if ( UserNameFromContext < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      {
        v14 = 39;
        goto LABEL_35;
      }
    }
  }
LABEL_47:
  *(_QWORD *)(a1 + 440) = (unsigned int)*a2;
  if ( UserNameFromContext < 0 )
  {
    if ( v10 && !v5 )
      OncRpcSepInboundDestroyGssContext(v10, Timer_high, v8);
  }
  else
  {
    *(_QWORD *)(a1 + 1000) = v10;
    if ( !v5 )
      OncRpcSepInboundAddGssCtx(v10);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      40,
      WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids,
      (unsigned int)UserNameFromContext);
  return (unsigned int)UserNameFromContext;
}

```

## disassembly

```asm
0x14000bb64  mov     rax, rsp
0x14000bb67  push    rbx
0x14000bb68  push    rsi
0x14000bb69  push    rdi
0x14000bb6a  push    r12
0x14000bb6c  push    r14
0x14000bb6e  push    r15
0x14000bb70  sub     rsp, 58h
0x14000bb74  cmp     dword ptr [rcx+138h], 2
0x14000bb7b  lea     r12, WPP_GLOBAL_Control
0x14000bb82  mov     r15, rdx
0x14000bb85  mov     qword ptr [rax+8], 0
0x14000bb8d  mov     rsi, rcx
0x14000bb90  jnz     loc_14000BCB1
0x14000bb96  mov     edx, [rcx+148h]
0x14000bb9c  mov     r14b, 1
0x14000bb9f  lea     rcx, [rax+8]
0x14000bba3  call    OncRpcSepInboundQueryAndRefGssCtx
0x14000bba8  mov     edi, eax
0x14000bbaa  test    eax, eax
0x14000bbac  jns     short loc_14000BBEF
0x14000bbae  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bbb5  cmp     rcx, r12
0x14000bbb8  jz      short loc_14000BBE2
0x14000bbba  mov     edx, [rcx+2Ch]
0x14000bbbd  test    dl, 40h
0x14000bbc0  jz      short loc_14000BBE2
0x14000bbc2  mov     r9d, [rsi+148h]
0x14000bbc9  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x14000bbd0  mov     rcx, [rcx+18h]
0x14000bbd4  mov     edx, 22h ; '"'
0x14000bbd9  mov     [rsp+88h+var_68], eax
0x14000bbdd  call    WPP_SF_Dd
0x14000bbe2  mov     rbx, [rsp+88h+arg_0]
0x14000bbea  jmp     loc_14000BF04
0x14000bbef  movzx   eax, word ptr [rsi+0DCh]
0x14000bbf6  mov     ecx, 2
0x14000bbfb  mov     rbx, [rsp+88h+arg_0]
0x14000bc03  cmp     cx, ax
0x14000bc06  jnz     short loc_14000BC21
0x14000bc08  cmp     cx, [rbx+84h]
0x14000bc0f  jnz     short loc_14000BC63
0x14000bc11  mov     eax, [rsi+0E0h]
0x14000bc17  cmp     eax, [rbx+88h]
0x14000bc1d  jz      short loc_14000BC54
0x14000bc1f  jmp     short loc_14000BC63
0x14000bc21  mov     ecx, 17h
0x14000bc26  cmp     cx, ax
0x14000bc29  jnz     short loc_14000BC63
0x14000bc2b  cmp     cx, [rbx+84h]
0x14000bc32  jnz     short loc_14000BC63
0x14000bc34  mov     rax, [rsi+0E4h]
0x14000bc3b  cmp     rax, [rbx+8Ch]
0x14000bc42  jnz     short loc_14000BC63
0x14000bc44  mov     rax, [rsi+0ECh]
0x14000bc4b  cmp     rax, [rbx+94h]
0x14000bc52  jnz     short loc_14000BC63
0x14000bc54  mov     ecx, 3
0x14000bc59  lea     eax, [rcx-2]
0x14000bc5c  lock cmpxchg [rbx+44h], ecx
0x14000bc61  jz      short loc_14000BCA3
0x14000bc63  mov     rcx, rbx
0x14000bc66  call    NfsStandardHeaderDereferenceNoType
0x14000bc6b  xor     ebx, ebx
0x14000bc6d  mov     edi, 0C0000022h
0x14000bc72  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bc79  cmp     rcx, r12
0x14000bc7c  jz      loc_14000BF04
0x14000bc82  mov     eax, [rcx+2Ch]
0x14000bc85  test    al, 40h
0x14000bc87  jz      loc_14000BF04
0x14000bc8d  mov     rcx, [rcx+18h]
0x14000bc91  lea     edx, [rbx+23h]
0x14000bc94  mov     r9d, edi
0x14000bc97  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x14000bc9e  call    WPP_SF_d
0x14000bca3  test    edi, edi
0x14000bca5  js      loc_14000BF04
0x14000bcab  lea     r8, [rbx+58h]
0x14000bcaf  jmp     short loc_14000BCE5
0x14000bcb1  mov     rcx, cs:qword_14001AA00
0x14000bcb8  lea     r8, [rsp+88h+arg_0]
0x14000bcc0  xor     r14b, r14b
0x14000bcc3  call    NfsMemMgrStructureAllocateByHandle
0x14000bcc8  mov     edi, eax
0x14000bcca  test    eax, eax
0x14000bccc  js      loc_14000BBE2
0x14000bcd2  mov     rbx, [rsp+88h+arg_0]
0x14000bcda  mov     rcx, rbx
0x14000bcdd  call    NfsStandardHeaderReferenceNoType
0x14000bce2  xor     r8d, r8d
0x14000bce5  mov     r9, [rsi+160h]
0x14000bcec  lea     rax, [rbx+68h]
0x14000bcf0  mov     [rsp+88h+var_48], rax; PTimeStamp
0x14000bcf5  lea     rcx, [rsi+400h]
0x14000bcfc  mov     eax, [rsi+158h]
0x14000bd02  lea     rdx, [rsi+3F8h]
0x14000bd09  mov     [rsp+88h+var_50], rcx; __int64
0x14000bd0e  lea     r12, [rbx+58h]
0x14000bd12  mov     [rsp+88h+var_58], rdx; __int64
0x14000bd17  lea     rcx, phCredential; phCredential
0x14000bd1e  mov     [rsp+88h+var_60], r12; PCtxtHandle
0x14000bd23  mov     rdx, r15
0x14000bd26  mov     [rsp+88h+var_68], eax; int
0x14000bd2a  call    OncRpcSepServerEstablishContext
0x14000bd2f  mov     edi, eax
0x14000bd31  test    eax, eax
0x14000bd33  jns     short loc_14000BD71
0x14000bd35  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bd3c  lea     rax, WPP_GLOBAL_Control
0x14000bd43  cmp     rcx, rax
0x14000bd46  jz      short loc_14000BD75
0x14000bd48  mov     eax, [rcx+2Ch]
0x14000bd4b  test    al, 40h
0x14000bd4d  jz      short loc_14000BD75
0x14000bd4f  mov     r9d, [rsi+148h]
0x14000bd56  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x14000bd5d  mov     rcx, [rcx+18h]
0x14000bd61  mov     edx, 24h ; '$'
0x14000bd66  mov     [rsp+88h+var_68], edi
0x14000bd6a  call    WPP_SF_Dd
0x14000bd6f  jmp     short loc_14000BD75
0x14000bd71  or      dword ptr [rbx+70h], 1
0x14000bd75  mov     eax, [r15]
0x14000bd78  cmp     eax, 1
0x14000bd7b  jnz     short loc_14000BD9F
0x14000bd7d  inc     dword ptr [rbx+48h]
0x14000bd80  lea     rdx, [rsi+0DCh]
0x14000bd87  lea     rcx, [rbx+84h]
0x14000bd8e  call    OncRpcCopyAddress
0x14000bd93  mov     dword ptr [rbx+44h], 1
0x14000bd9a  jmp     loc_14000BE61
0x14000bd9f  test    eax, eax
0x14000bda1  jnz     loc_14000BE5A
0x14000bda7  mov     dword ptr [rbx+44h], 2
0x14000bdae  lea     rdx, [rsi+0DCh]
0x14000bdb5  lea     rcx, [rbx+84h]
0x14000bdbc  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x14000bdc3  call    OncRpcCopyAddress
0x14000bdc8  mov     rdx, r15
0x14000bdcb  mov     rcx, rbx
0x14000bdce  call    OncRpcSepQueryUserNameFromContext
0x14000bdd3  mov     edi, eax
0x14000bdd5  test    eax, eax
0x14000bdd7  jns     short loc_14000BE20
0x14000bdd9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bde0  lea     r12, WPP_GLOBAL_Control
0x14000bde7  cmp     rcx, r12
0x14000bdea  jz      loc_14000BF04
0x14000bdf0  mov     eax, [rcx+2Ch]
0x14000bdf3  test    al, 40h
0x14000bdf5  jz      loc_14000BF04
0x14000bdfb  mov     edx, 25h ; '%'
0x14000be00  mov     r9d, [rsi+148h]
0x14000be07  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x14000be0e  mov     rcx, [rcx+18h]
0x14000be12  mov     [rsp+88h+var_68], edi
0x14000be16  call    WPP_SF_Dd
0x14000be1b  jmp     loc_14000BF04
0x14000be20  mov     rdx, r15
0x14000be23  mov     rcx, rbx
0x14000be26  call    OncRpcSepQuerySizesFromContext
0x14000be2b  mov     edi, eax
0x14000be2d  test    eax, eax
0x14000be2f  jns     short loc_14000BE69
0x14000be31  mov     rcx, cs:WPP_GLOBAL_Control
0x14000be38  lea     r12, WPP_GLOBAL_Control
0x14000be3f  cmp     rcx, r12
0x14000be42  jz      loc_14000BF04
0x14000be48  mov     eax, [rcx+2Ch]
0x14000be4b  test    al, 40h
0x14000be4d  jz      loc_14000BF04
0x14000be53  mov     edx, 26h ; '&'
0x14000be58  jmp     short loc_14000BE00
0x14000be5a  mov     dword ptr [rbx+44h], 4
0x14000be61  test    edi, edi
0x14000be63  js      loc_14000BEFD
0x14000be69  cmp     dword ptr [r15], 0
0x14000be6d  mov     dword ptr [rsi+1C0h], 40h ; '@'
0x14000be77  jnz     loc_14000BEFD
0x14000be7d  lea     rax, [rsi+438h]
0x14000be84  mov     dword ptr [rsp+88h+arg_0], 40000000h
0x14000be8f  mov     [rsp+88h+var_50], rax
0x14000be94  lea     rdx, [rsi+178h]
0x14000be9b  mov     dword ptr [rsp+88h+var_58], 40h ; '@'
0x14000bea3  lea     r9, [rsp+88h+arg_0]
0x14000beab  mov     [rsp+88h+var_60], rdx
0x14000beb0  xor     r8d, r8d
0x14000beb3  mov     [rsi+430h], rdx
0x14000beba  mov     rcx, r12
0x14000bebd  mov     rdx, r15
0x14000bec0  mov     dword ptr [rax], 40h ; '@'
0x14000bec6  mov     [rsp+88h+var_68], 4
0x14000bece  call    OncRpcSeMakeSignature
0x14000bed3  mov     edi, eax
0x14000bed5  test    eax, eax
0x14000bed7  jns     short loc_14000BEFD
0x14000bed9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bee0  lea     r12, WPP_GLOBAL_Control
0x14000bee7  cmp     rcx, r12
0x14000beea  jz      short loc_14000BF04
0x14000beec  mov     eax, [rcx+2Ch]
0x14000beef  test    al, 40h
0x14000bef1  jz      short loc_14000BF04
0x14000bef3  mov     edx, 27h ; '''
0x14000bef8  jmp     loc_14000BE00
0x14000befd  lea     r12, WPP_GLOBAL_Control
0x14000bf04  mov     eax, [r15]
0x14000bf07  mov     [rsi+1B8h], eax
0x14000bf0d  mov     dword ptr [rsi+1BCh], 0
0x14000bf17  test    edi, edi
0x14000bf19  js      short loc_14000BF31
0x14000bf1b  mov     [rsi+3E8h], rbx
0x14000bf22  test    r14b, r14b
0x14000bf25  jnz     short loc_14000BF43
0x14000bf27  mov     rcx, rbx
0x14000bf2a  call    OncRpcSepInboundAddGssCtx
0x14000bf2f  jmp     short loc_14000BF43
0x14000bf31  test    rbx, rbx
0x14000bf34  jz      short loc_14000BF43
0x14000bf36  test    r14b, r14b
0x14000bf39  jnz     short loc_14000BF43
0x14000bf3b  mov     rcx, rbx
0x14000bf3e  call    OncRpcSepInboundDestroyGssContext
0x14000bf43  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bf4a  cmp     rcx, r12
0x14000bf4d  jz      short loc_14000BF6E
0x14000bf4f  mov     eax, [rcx+2Ch]
0x14000bf52  test    al, 1
0x14000bf54  jz      short loc_14000BF6E
0x14000bf56  mov     rcx, [rcx+18h]
0x14000bf5a  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x14000bf61  mov     edx, 28h ; '('
0x14000bf66  mov     r9d, edi
0x14000bf69  call    WPP_SF_d
0x14000bf6e  mov     eax, edi
0x14000bf70  add     rsp, 58h
0x14000bf74  pop     r15
0x14000bf76  pop     r14
0x14000bf78  pop     r12
0x14000bf7a  pop     rdi
0x14000bf7b  pop     rsi
0x14000bf7c  pop     rbx
0x14000bf7d  retn
```
