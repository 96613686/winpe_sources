# CopyClientString

- ea: `0x180010510`
- end: `0x18001078c`
- name: `CopyClientString`
- size: `636`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180002ef0`

## callees

- `0x1800061a0`
- `0x180006d00`
- `0x180009770`
- `0x180010510`
- `0x180011fec`
- `0x1800185b8`
- `0x180033500`
- `0x180038010`

## import_xrefs

- `ntdll!RtlAnsiStringToUnicodeString` at `0x180010723`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180010723`

## pseudocode

```c
__int64 __fastcall CopyClientString(__int64 a1, unsigned int a2, char a3, struct _UNICODE_STRING *a4)
{
  int v4; // ebx
  __int64 Memory; // rax
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  unsigned int v12; // edi
  NTSTATUS v13; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  struct _STRING SourceString; // [rsp+30h] [rbp-48h] BYREF

  v4 = 0;
  *(_DWORD *)&a4->Length = 0;
  a4->Buffer = 0;
  SourceString = 0;
  if ( !a1 )
    goto LABEL_36;
  if ( !a2 )
  {
    Memory = DigestAllocateMemory(2u);
    a4->Buffer = (PWSTR)Memory;
    if ( Memory )
    {
      a4->MaximumLength = 2;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_5a1eec0057703498b5d13460810c8614_Traceguids);
      v4 = -2146893056;
    }
    goto LABEL_36;
  }
  v9 = (a3 != 0) + 1;
  if ( a2 > 0xFFFF / v9 - 1 )
  {
    v4 = -1073741811;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_36;
    v11 = 33;
    goto LABEL_13;
  }
  v12 = v9 * (a2 + 1);
  SourceString.Buffer = (PCHAR)DigestAllocateMemory(v12);
  if ( !SourceString.Buffer )
  {
    v4 = -2146893056;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_36;
    v11 = 34;
    goto LABEL_13;
  }
  SourceString.MaximumLength = v12;
  SourceString.Length = v12 - ((a3 != 0) + 1);
  v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, PCHAR, __int64))(*(_QWORD *)&g_LsaFunctions + 80LL))(
          0,
          v12 - v9,
          SourceString.Buffer,
          a1);
  v4 = v13;
  if ( v13 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_36;
    v15 = 35;
    goto LABEL_35;
  }
  if ( a3 )
  {
    a4->Buffer = (PWSTR)SourceString.Buffer;
    a4->Length = v12 - ((a3 != 0) + 1);
    a4->MaximumLength = v12;
    SourceString.Buffer = 0;
    return (unsigned int)v4;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_5a1eec0057703498b5d13460810c8614_Traceguids);
  v4 = UnicodeStringAllocate((__int64)a4, SourceString.Length);
  if ( v4 >= 0 )
  {
    v13 = RtlAnsiStringToUnicodeString(a4, &SourceString, 0);
    v4 = v13;
    if ( v13 >= 0 )
      goto LABEL_36;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_36;
    v15 = 38;
LABEL_35:
    WPP_SF_d(v14[2], v15, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, (unsigned int)v13);
    goto LABEL_36;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_36;
  v11 = 37;
LABEL_13:
  WPP_SF_(v10[2], v11, WPP_5a1eec0057703498b5d13460810c8614_Traceguids);
LABEL_36:
  if ( SourceString.Buffer )
  {
    DigestFreeMemory(SourceString.Buffer);
    SourceString.Buffer = 0;
  }
  if ( v4 < 0 )
    UnicodeStringFree(a4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180010510  push    rbx
0x180010512  push    rbp
0x180010513  push    rsi
0x180010514  push    rdi
0x180010515  push    r14
0x180010517  push    r15
0x180010519  sub     rsp, 48h
0x18001051d  xor     eax, eax
0x18001051f  xor     ebx, ebx
0x180010521  mov     [r9], eax
0x180010524  xorps   xmm0, xmm0
0x180010527  mov     [r9+8], rax
0x18001052b  mov     rsi, r9
0x18001052e  mov     bpl, r8b
0x180010531  mov     edi, edx
0x180010533  mov     r15, rcx
0x180010536  movups  xmmword ptr [rsp+78h+SourceString.Length], xmm0
0x18001053b  test    rcx, rcx
0x18001053e  jz      loc_180010759
0x180010544  test    edx, edx
0x180010546  jnz     short loc_18001059A
0x180010548  lea     edi, [rdx+2]
0x18001054b  mov     ecx, edi; Size
0x18001054d  call    DigestAllocateMemory
0x180010552  mov     [rsi+8], rax
0x180010556  test    rax, rax
0x180010559  jnz     short loc_180010591
0x18001055b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010562  lea     rdi, WPP_GLOBAL_Control
0x180010569  cmp     rcx, rdi
0x18001056c  jz      short loc_180010587
0x18001056e  test    byte ptr [rcx+1Ch], 1
0x180010572  jz      short loc_180010587
0x180010574  mov     rcx, [rcx+10h]
0x180010578  lea     edx, [rbx+20h]
0x18001057b  lea     r8, WPP_5a1eec0057703498b5d13460810c8614_Traceguids
0x180010582  call    WPP_SF_
0x180010587  mov     ebx, 80090300h
0x18001058c  jmp     loc_180010759
0x180010591  mov     [rsi+2], di
0x180010595  jmp     loc_180010759
0x18001059a  mov     al, bpl
0x18001059d  neg     al
0x18001059f  mov     eax, 0FFFFh
0x1800105a4  sbb     ebx, ebx
0x1800105a6  xor     edx, edx
0x1800105a8  neg     ebx
0x1800105aa  inc     ebx
0x1800105ac  div     ebx
0x1800105ae  dec     eax
0x1800105b0  cmp     edi, eax
0x1800105b2  jbe     short loc_1800105F4
0x1800105b4  mov     ebx, 0C000000Dh
0x1800105b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800105c0  lea     rdi, WPP_GLOBAL_Control
0x1800105c7  cmp     rcx, rdi
0x1800105ca  jz      loc_180010759
0x1800105d0  test    byte ptr [rcx+1Ch], 1
0x1800105d4  jz      loc_180010759
0x1800105da  mov     edx, 21h ; '!'
0x1800105df  mov     rcx, [rcx+10h]
0x1800105e3  lea     r8, WPP_5a1eec0057703498b5d13460810c8614_Traceguids
0x1800105ea  call    WPP_SF_
0x1800105ef  jmp     loc_180010759
0x1800105f4  inc     edi
0x1800105f6  imul    edi, ebx
0x1800105f9  mov     ecx, edi; Size
0x1800105fb  call    DigestAllocateMemory
0x180010600  mov     [rsp+78h+SourceString.Buffer], rax
0x180010605  test    rax, rax
0x180010608  jnz     short loc_180010635
0x18001060a  mov     ebx, 80090300h
0x18001060f  mov     rcx, cs:WPP_GLOBAL_Control
0x180010616  lea     rdi, WPP_GLOBAL_Control
0x18001061d  cmp     rcx, rdi
0x180010620  jz      loc_180010759
0x180010626  test    byte ptr [rcx+1Ch], 1
0x18001062a  jz      loc_180010759
0x180010630  lea     edx, [rax+22h]
0x180010633  jmp     short loc_1800105DF
0x180010635  mov     rax, cs:g_LsaFunctions
0x18001063c  mov     edx, edi
0x18001063e  mov     r8, [rsp+78h+SourceString.Buffer]
0x180010643  movzx   r14d, di
0x180010647  mov     [rsp+78h+SourceString.MaximumLength], di
0x18001064c  sub     r14w, bx
0x180010650  mov     [rsp+78h+SourceString.Length], r14w
0x180010656  sub     edx, ebx
0x180010658  mov     rax, [rax+50h]
0x18001065c  mov     r9, r15
0x18001065f  xor     ecx, ecx
0x180010661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010666  mov     ebx, eax
0x180010668  test    eax, eax
0x18001066a  jns     short loc_180010697
0x18001066c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010673  lea     rdi, WPP_GLOBAL_Control
0x18001067a  cmp     rcx, rdi
0x18001067d  jz      loc_180010759
0x180010683  test    byte ptr [rcx+1Ch], 1
0x180010687  jz      loc_180010759
0x18001068d  mov     edx, 23h ; '#'
0x180010692  jmp     loc_180010746
0x180010697  test    bpl, bpl
0x18001069a  jz      short loc_1800106BB
0x18001069c  mov     rax, [rsp+78h+SourceString.Buffer]
0x1800106a1  mov     [rsi+8], rax
0x1800106a5  mov     [rsi], r14w
0x1800106a9  mov     [rsi+2], di
0x1800106ad  mov     [rsp+78h+SourceString.Buffer], 0
0x1800106b6  jmp     loc_18001077D
0x1800106bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800106c2  lea     rdi, WPP_GLOBAL_Control
0x1800106c9  cmp     rcx, rdi
0x1800106cc  jz      short loc_1800106E9
0x1800106ce  test    byte ptr [rcx+1Ch], 4
0x1800106d2  jz      short loc_1800106E9
0x1800106d4  mov     rcx, [rcx+10h]
0x1800106d8  lea     r8, WPP_5a1eec0057703498b5d13460810c8614_Traceguids
0x1800106df  mov     edx, 24h ; '$'
0x1800106e4  call    WPP_SF_
0x1800106e9  movzx   edx, [rsp+78h+SourceString.Length]
0x1800106ee  mov     rcx, rsi
0x1800106f1  call    UnicodeStringAllocate
0x1800106f6  mov     ebx, eax
0x1800106f8  test    eax, eax
0x1800106fa  jns     short loc_180010718
0x1800106fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180010703  cmp     rcx, rdi
0x180010706  jz      short loc_180010759
0x180010708  test    byte ptr [rcx+1Ch], 1
0x18001070c  jz      short loc_180010759
0x18001070e  mov     edx, 25h ; '%'
0x180010713  jmp     loc_1800105DF
0x180010718  xor     r8d, r8d; AllocateDestinationString
0x18001071b  lea     rdx, [rsp+78h+SourceString]; SourceString
0x180010720  mov     rcx, rsi; DestinationString
0x180010723  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180010729  mov     ebx, eax
0x18001072b  test    eax, eax
0x18001072d  jns     short loc_180010759
0x18001072f  mov     rcx, cs:WPP_GLOBAL_Control
0x180010736  cmp     rcx, rdi
0x180010739  jz      short loc_180010759
0x18001073b  test    byte ptr [rcx+1Ch], 1
0x18001073f  jz      short loc_180010759
0x180010741  mov     edx, 26h ; '&'
0x180010746  mov     rcx, [rcx+10h]
0x18001074a  lea     r8, WPP_5a1eec0057703498b5d13460810c8614_Traceguids
0x180010751  mov     r9d, eax
0x180010754  call    WPP_SF_d
0x180010759  mov     rcx, [rsp+78h+SourceString.Buffer]; hMem
0x18001075e  test    rcx, rcx
0x180010761  jz      short loc_180010771
0x180010763  call    DigestFreeMemory
0x180010768  mov     [rsp+78h+SourceString.Buffer], 0
0x180010771  test    ebx, ebx
0x180010773  jns     short loc_18001077D
0x180010775  mov     rcx, rsi
0x180010778  call    UnicodeStringFree
0x18001077d  mov     eax, ebx
0x18001077f  add     rsp, 48h
0x180010783  pop     r15
0x180010785  pop     r14
0x180010787  pop     rdi
0x180010788  pop     rsi
0x180010789  pop     rbp
0x18001078a  pop     rbx
0x18001078b  retn
```
