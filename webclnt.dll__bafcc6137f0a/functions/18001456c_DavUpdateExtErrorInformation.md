# DavUpdateExtErrorInformation

- ea: `0x18001456c`
- end: `0x1800146f6`
- name: `DavUpdateExtErrorInformation`
- size: `394`
- prototype: `__int64 __fastcall(HINTERNET hRequest, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000d9e4`
- `0x180013c08`

## callees

- `0x18000b7dc`
- `0x1800114fc`
- `0x18001171c`
- `0x18001456c`
- `0x1800146fc`
- `0x180014820`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800146df`
- `KERNEL32!LocalFree` at `0x1800146df`

## pseudocode

```c
__int64 __fastcall DavUpdateExtErrorInformation(HINTERNET hRequest, __int64 a2)
{
  _WORD *v2; // r14
  HLOCAL v5; // rdi
  unsigned int FBAAuthRequiredExtErrorInfo; // esi
  unsigned int ExtErrorInfo; // eax
  int v8; // r9d
  __int64 v9; // rcx
  _WORD *v10; // rdx
  __int64 v11; // rax
  _WORD *v12; // rcx
  __int64 v14; // [rsp+78h] [rbp+48h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp+50h] BYREF
  _WORD *v16; // [rsp+88h] [rbp+58h] BYREF

  v2 = (_WORD *)(a2 + 7120);
  *(_DWORD *)(a2 + 7116) = 0;
  *(_WORD *)(a2 + 7120) = 0;
  LODWORD(v14) = 0;
  v5 = 0;
  hMem = 0;
  v16 = 0;
  FBAAuthRequiredExtErrorInfo = DavGetFBAAuthRequiredExtErrorInfo(hRequest);
  if ( !FBAAuthRequiredExtErrorInfo )
  {
    *(_DWORD *)(a2 + 7116) = 917656;
LABEL_16:
    if ( *(_DWORD *)(a2 + 48) == 4 || !*(_DWORD *)(a2 + 48) )
    {
      LODWORD(v14) = 0;
      DavUpdateExtErrorInformationForThread(hRequest, (__int64)&v14);
    }
    goto LABEL_19;
  }
  ExtErrorInfo = DavGetExtErrorInfo(hRequest, &hMem);
  v5 = hMem;
  FBAAuthRequiredExtErrorInfo = ExtErrorInfo;
  if ( !ExtErrorInfo )
  {
    if ( !hMem )
      return FBAAuthRequiredExtErrorInfo;
    FBAAuthRequiredExtErrorInfo = DavVerifyAndGetExtErrorInfo(hMem, &v14, &v16);
    if ( FBAAuthRequiredExtErrorInfo )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          168,
          WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids,
          FBAAuthRequiredExtErrorInfo);
      goto LABEL_19;
    }
    v8 = v14;
    v9 = 2147483646;
    v10 = v16;
    v11 = 1024;
    *(_DWORD *)(a2 + 7116) = v14;
    do
    {
      if ( !v9 )
        break;
      if ( !*v10 )
        break;
      *v2++ = *v10++;
      --v9;
      --v11;
    }
    while ( v11 );
    v12 = v2 - 1;
    if ( v11 )
      v12 = v2;
    *v12 = 0;
    if ( !v8 )
      goto LABEL_19;
    goto LABEL_16;
  }
LABEL_19:
  if ( v5 )
    LocalFree(v5);
  return FBAAuthRequiredExtErrorInfo;
}

```

## disassembly

```asm
0x18001456c  push    rbp
0x18001456e  push    rbx
0x18001456f  push    rsi
0x180014570  push    rdi
0x180014571  push    r12
0x180014573  push    r14
0x180014575  push    r15
0x180014577  mov     rbp, rsp
0x18001457a  sub     rsp, 30h
0x18001457e  xor     r12d, r12d
0x180014581  lea     r14, [rdx+1BD0h]
0x180014588  mov     [rdx+1BCCh], r12d
0x18001458f  mov     rbx, rdx
0x180014592  mov     [r14], r12w
0x180014596  mov     r15, rcx
0x180014599  mov     dword ptr [rbp+arg_8], r12d
0x18001459d  mov     edi, r12d
0x1800145a0  mov     [rbp+hMem], r12
0x1800145a4  mov     [rbp+arg_18], r12
0x1800145a8  call    DavGetFBAAuthRequiredExtErrorInfo
0x1800145ad  mov     esi, eax
0x1800145af  test    eax, eax
0x1800145b1  jnz     short loc_1800145C2
0x1800145b3  mov     dword ptr [rbx+1BCCh], 0E0098h
0x1800145bd  jmp     loc_18001468A
0x1800145c2  lea     rdx, [rbp+hMem]
0x1800145c6  mov     rcx, r15; hRequest
0x1800145c9  call    DavGetExtErrorInfo
0x1800145ce  mov     rdi, [rbp+hMem]
0x1800145d2  mov     esi, eax
0x1800145d4  test    eax, eax
0x1800145d6  jnz     loc_1800146D7
0x1800145dc  test    rdi, rdi
0x1800145df  jz      loc_1800146E5
0x1800145e5  lea     r8, [rbp+arg_18]
0x1800145e9  mov     rcx, rdi
0x1800145ec  lea     rdx, [rbp+arg_8]
0x1800145f0  call    DavVerifyAndGetExtErrorInfo
0x1800145f5  mov     esi, eax
0x1800145f7  test    eax, eax
0x1800145f9  jz      short loc_180014639
0x1800145fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180014602  lea     rax, WPP_GLOBAL_Control
0x180014609  cmp     rcx, rax
0x18001460c  jz      loc_1800146D7
0x180014612  test    byte ptr [rcx+1Ch], 1
0x180014616  jz      loc_1800146D7
0x18001461c  mov     rcx, [rcx+10h]
0x180014620  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180014627  mov     edx, 0A8h
0x18001462c  mov     r9d, esi
0x18001462f  call    WPP_SF_d
0x180014634  jmp     loc_1800146D7
0x180014639  mov     r9d, dword ptr [rbp+arg_8]
0x18001463d  mov     ecx, 7FFFFFFEh
0x180014642  mov     rdx, [rbp+arg_18]
0x180014646  mov     eax, 400h
0x18001464b  mov     [rbx+1BCCh], r9d
0x180014652  test    rcx, rcx
0x180014655  jz      short loc_180014676
0x180014657  movzx   r8d, word ptr [rdx]
0x18001465b  test    r8w, r8w
0x18001465f  jz      short loc_180014676
0x180014661  mov     [r14], r8w
0x180014665  add     rdx, 2
0x180014669  add     r14, 2
0x18001466d  dec     rcx
0x180014670  sub     rax, 1
0x180014674  jnz     short loc_180014652
0x180014676  test    rax, rax
0x180014679  lea     rcx, [r14-2]
0x18001467d  cmovnz  rcx, r14
0x180014681  mov     [rcx], r12w
0x180014685  test    r9d, r9d
0x180014688  jz      short loc_1800146D7
0x18001468a  cmp     dword ptr [rbx+30h], 4
0x18001468e  jnz     short loc_1800146A7
0x180014690  mov     r9, [rbx+290h]
0x180014697  lea     rdx, [rbx+280h]
0x18001469e  mov     r8, [rbx+288h]
0x1800146a5  jmp     short loc_1800146C2
0x1800146a7  cmp     [rbx+30h], r12d
0x1800146ab  jnz     short loc_1800146D7
0x1800146ad  mov     r9, [rbx+298h]
0x1800146b4  lea     rdx, [rbx+284h]
0x1800146bb  mov     r8, [rbx+290h]
0x1800146c2  lea     rax, [rbp+arg_8]
0x1800146c6  mov     dword ptr [rbp+arg_8], r12d
0x1800146ca  mov     rcx, r15; hRequest
0x1800146cd  mov     [rsp+30h+var_10], rax; __int64
0x1800146d2  call    DavUpdateExtErrorInformationForThread
0x1800146d7  test    rdi, rdi
0x1800146da  jz      short loc_1800146E5
0x1800146dc  mov     rcx, rdi; hMem
0x1800146df  call    cs:__imp_LocalFree
0x1800146e5  mov     eax, esi
0x1800146e7  add     rsp, 30h
0x1800146eb  pop     r15
0x1800146ed  pop     r14
0x1800146ef  pop     r12
0x1800146f1  pop     rdi
0x1800146f2  pop     rsi
0x1800146f3  pop     rbx
0x1800146f4  pop     rbp
0x1800146f5  retn
```
