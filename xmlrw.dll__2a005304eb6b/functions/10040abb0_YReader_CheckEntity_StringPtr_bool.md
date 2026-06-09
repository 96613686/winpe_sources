# YReader::CheckEntity(StringPtr *,bool)

- ea: `0x10040abb0`
- end: `0x10040ae44`
- name: `?CheckEntity@YReader@@AEAAPEAVDeclEntity@@PEAUStringPtr@@_N@Z`
- size: `660`
- prototype: `struct DeclEntity *__fastcall(YReader *__hidden this, struct StringPtr *, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x100407ec0`
- `0x10040bb50`

## callees

- `0x100401780`
- `0x10040abb0`
- `0x100416bc0`
- `0x1004394f0`
- `0x100439df0`

## pseudocode

```c
void ***__fastcall YReader::CheckEntity(YReader *this, struct StringPtr *a2, char a3)
{
  int v3; // eax
  __int64 v5; // r9
  void ***v7; // rbx
  __int64 v8; // rax
  unsigned int v9; // ecx
  void (__fastcall *v10)(YReader *); // rax
  __int64 v11; // rax
  unsigned int v12; // ecx

  v3 = *((_DWORD *)a2 + 2);
  v5 = *(_QWORD *)a2;
  if ( v3 == 4 )
  {
    if ( *(_WORD *)v5 == 113 )
    {
      if ( *(_QWORD *)v5 == *CodeStringPtr::quot )
      {
        v7 = &s_EntityQuot;
        goto LABEL_5;
      }
    }
    else if ( *(_WORD *)v5 == 97 && *(_QWORD *)v5 == *CodeStringPtr::apos )
    {
      v7 = &s_EntityApos;
      goto LABEL_5;
    }
  }
  else if ( v3 == 2 )
  {
    if ( *(_WORD *)v5 == 103 )
    {
      if ( *(_DWORD *)v5 == *CodeStringPtr::gt )
      {
        v7 = &s_EntityGt;
        goto LABEL_5;
      }
    }
    else if ( *(_WORD *)v5 == 108 && *(_DWORD *)v5 == *CodeStringPtr::lt )
    {
      v7 = &s_EntityLt;
      goto LABEL_5;
    }
  }
  else if ( v3 == 3
         && *(_WORD *)v5 == 97
         && *(_DWORD *)v5 == *CodeStringPtr::amp
         && *(_WORD *)(v5 + 4) == *(_WORD *)(CodeStringPtr::amp + 4LL) )
  {
    v7 = &s_EntityAmp;
    goto LABEL_5;
  }
  v7 = (void ***)_htable<DeclEntity>::lookup((char *)this + 1336, a2);
  if ( !v7 )
  {
    v10 = (void (__fastcall *)(YReader *))*((_QWORD *)this + 188);
    if ( (v10 != YReader::ParseContent || v10 && *((_DWORD *)this + 378)) && !a3 )
      return v7;
    if ( *((_DWORD *)this + 464) )
      return v7;
    if ( !*((_BYTE *)this + 1787) )
    {
      if ( *(_QWORD *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 157) + 8LL))((char *)this + 1256) )
      {
        v11 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 157) + 40LL))((char *)this + 1256);
        v12 = *(_DWORD *)(v11 + 8);
        if ( v12 != dword_100450B38
          || memcmp(*(const void **)v11, CodeStringPtr::empty, 2LL * v12)
          || *((_BYTE *)this + 1794) )
        {
          return v7;
        }
      }
    }
LABEL_44:
    MXRRaiseException(-1072894393);
    __debugbreak();
  }
LABEL_5:
  if ( *((_BYTE *)v7 + 130) )
  {
    if ( !*((_DWORD *)this + 464) )
    {
      if ( *((_BYTE *)this + 1787) )
        goto LABEL_44;
      if ( !*(_QWORD *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 157) + 8LL))((char *)this + 1256) )
        goto LABEL_44;
      v8 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 157) + 40LL))((char *)this + 1256);
      v9 = *(_DWORD *)(v8 + 8);
      if ( v9 == dword_100450B38
        && !memcmp(*(const void **)v8, CodeStringPtr::empty, 2LL * v9)
        && !*((_BYTE *)this + 1794) )
      {
        goto LABEL_44;
      }
    }
  }
  if ( !v7[12] )
  {
    if ( v7[14] )
    {
      MXRRaiseException(-1072894392);
      JUMPOUT(0x10040AE43LL);
    }
    if ( a3 )
    {
      MXRRaiseException(-1072894391);
      __debugbreak();
    }
  }
  return v7;
}

```

## disassembly

```asm
0x10040abb0  mov     [rsp+arg_0], rbx
0x10040abb5  mov     [rsp+arg_8], rbp
0x10040abba  mov     [rsp+arg_10], rsi
0x10040abbf  push    rdi
0x10040abc0  sub     rsp, 20h
0x10040abc4  mov     eax, [rdx+8]
0x10040abc7  movzx   ebp, r8b
0x10040abcb  mov     r9, [rdx]
0x10040abce  mov     rdi, rcx
0x10040abd1  cmp     eax, 4
0x10040abd4  jnz     loc_10040ACC9
0x10040abda  movzx   eax, word ptr [r9]
0x10040abde  cmp     ax, 71h ; 'q'
0x10040abe2  jnz     loc_10040ACA0
0x10040abe8  mov     r8, cs:?quot@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::quot
0x10040abef  mov     rax, [r9]
0x10040abf2  cmp     rax, [r8]
0x10040abf5  jnz     loc_10040AD43
0x10040abfb  lea     rbx, ?s_EntityQuot@@3VDeclEntity@@A; DeclEntity s_EntityQuot
0x10040ac02  cmp     byte ptr [rbx+82h], 0
0x10040ac09  jz      loc_10040AE10
0x10040ac0f  cmp     dword ptr [rdi+740h], 0
0x10040ac16  jnz     loc_10040AE10
0x10040ac1c  cmp     byte ptr [rdi+6FBh], 0
0x10040ac23  jnz     loc_10040AE2E
0x10040ac29  mov     rax, [rdi+4E8h]
0x10040ac30  lea     rcx, [rdi+4E8h]
0x10040ac37  mov     rax, [rax+8]
0x10040ac3b  call    cs:__guard_dispatch_icall_fptr
0x10040ac41  cmp     qword ptr [rax], 0
0x10040ac45  jz      loc_10040AE2E
0x10040ac4b  mov     rax, [rdi+4E8h]
0x10040ac52  lea     rcx, [rdi+4E8h]
0x10040ac59  mov     rax, [rax+28h]
0x10040ac5d  call    cs:__guard_dispatch_icall_fptr
0x10040ac63  mov     ecx, [rax+8]
0x10040ac66  cmp     ecx, cs:dword_100450B38
0x10040ac6c  jnz     loc_10040AE10
0x10040ac72  mov     rdx, cs:?empty@CodeStringPtr@@2UStringPtr@@A; Buf2
0x10040ac79  mov     r8d, ecx
0x10040ac7c  mov     rcx, [rax]; Buf1
0x10040ac7f  add     r8, r8; Size
0x10040ac82  call    memcmp
0x10040ac87  test    eax, eax
0x10040ac89  jnz     loc_10040AE10
0x10040ac8f  cmp     [rdi+702h], al
0x10040ac95  jz      loc_10040AE2E
0x10040ac9b  jmp     loc_10040AE10
0x10040aca0  cmp     ax, 61h ; 'a'
0x10040aca4  jnz     loc_10040AD43
0x10040acaa  mov     rcx, cs:?apos@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::apos
0x10040acb1  mov     rax, [r9]
0x10040acb4  cmp     rax, [rcx]
0x10040acb7  jnz     loc_10040AD43
0x10040acbd  lea     rbx, ?s_EntityApos@@3VDeclEntity@@A; DeclEntity s_EntityApos
0x10040acc4  jmp     loc_10040AC02
0x10040acc9  cmp     eax, 2
0x10040accc  jnz     short loc_10040AD12
0x10040acce  movzx   eax, word ptr [r9]
0x10040acd2  cmp     ax, 67h ; 'g'
0x10040acd6  jnz     short loc_10040ACF2
0x10040acd8  mov     rcx, cs:?gt@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::gt
0x10040acdf  mov     eax, [r9]
0x10040ace2  cmp     eax, [rcx]
0x10040ace4  jnz     short loc_10040AD43
0x10040ace6  lea     rbx, ?s_EntityGt@@3VDeclEntity@@A; DeclEntity s_EntityGt
0x10040aced  jmp     loc_10040AC02
0x10040acf2  cmp     ax, 6Ch ; 'l'
0x10040acf6  jnz     short loc_10040AD43
0x10040acf8  mov     rcx, cs:?lt@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::lt
0x10040acff  mov     eax, [r9]
0x10040ad02  cmp     eax, [rcx]
0x10040ad04  jnz     short loc_10040AD43
0x10040ad06  lea     rbx, ?s_EntityLt@@3VDeclEntity@@A; DeclEntity s_EntityLt
0x10040ad0d  jmp     loc_10040AC02
0x10040ad12  cmp     eax, 3
0x10040ad15  jnz     short loc_10040AD43
0x10040ad17  cmp     word ptr [r9], 61h ; 'a'
0x10040ad1c  jnz     short loc_10040AD43
0x10040ad1e  mov     rcx, cs:?amp@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::amp
0x10040ad25  mov     eax, [r9]
0x10040ad28  cmp     eax, [rcx]
0x10040ad2a  jnz     short loc_10040AD43
0x10040ad2c  movzx   eax, word ptr [r9+4]
0x10040ad31  cmp     ax, [rcx+4]
0x10040ad35  jnz     short loc_10040AD43
0x10040ad37  lea     rbx, ?s_EntityAmp@@3VDeclEntity@@A; DeclEntity s_EntityAmp
0x10040ad3e  jmp     loc_10040AC02
0x10040ad43  lea     rcx, [rdi+538h]
0x10040ad4a  call    ?lookup@?$_htable@VDeclEntity@@@@QEAAPEAVDeclEntity@@PEAUStringPtr@@@Z; _htable<DeclEntity>::lookup(StringPtr *)
0x10040ad4f  mov     rbx, rax
0x10040ad52  test    rax, rax
0x10040ad55  jnz     loc_10040AC02
0x10040ad5b  mov     rax, [rdi+5E0h]
0x10040ad62  lea     rcx, ?ParseContent@YReader@@AEAAXXZ; YReader::ParseContent(void)
0x10040ad69  cmp     rax, rcx
0x10040ad6c  jnz     short loc_10040AD7B
0x10040ad6e  test    rax, rax
0x10040ad71  jz      short loc_10040AD80
0x10040ad73  cmp     [rdi+5E8h], ebx
0x10040ad79  jz      short loc_10040AD80
0x10040ad7b  test    bpl, bpl
0x10040ad7e  jz      short loc_10040ADF8
0x10040ad80  cmp     dword ptr [rdi+740h], 0
0x10040ad87  jnz     short loc_10040ADF8
0x10040ad89  cmp     byte ptr [rdi+6FBh], 0
0x10040ad90  jnz     loc_10040AE2E
0x10040ad96  mov     rax, [rdi+4E8h]
0x10040ad9d  lea     rcx, [rdi+4E8h]
0x10040ada4  mov     rax, [rax+8]
0x10040ada8  call    cs:__guard_dispatch_icall_fptr
0x10040adae  cmp     qword ptr [rax], 0
0x10040adb2  jz      short loc_10040AE2E
0x10040adb4  mov     rax, [rdi+4E8h]
0x10040adbb  lea     rcx, [rdi+4E8h]
0x10040adc2  mov     rax, [rax+28h]
0x10040adc6  call    cs:__guard_dispatch_icall_fptr
0x10040adcc  mov     ecx, [rax+8]
0x10040adcf  cmp     ecx, cs:dword_100450B38
0x10040add5  jnz     short loc_10040ADF8
0x10040add7  mov     rdx, cs:?empty@CodeStringPtr@@2UStringPtr@@A; Buf2
0x10040adde  mov     r8d, ecx
0x10040ade1  mov     rcx, [rax]; Buf1
0x10040ade4  add     r8, r8; Size
0x10040ade7  call    memcmp
0x10040adec  test    eax, eax
0x10040adee  jnz     short loc_10040ADF8
0x10040adf0  cmp     [rdi+702h], al
0x10040adf6  jz      short loc_10040AE2E
0x10040adf8  mov     rbp, [rsp+28h+arg_8]
0x10040adfd  mov     rax, rbx
0x10040ae00  mov     rbx, [rsp+28h+arg_0]
0x10040ae05  mov     rsi, [rsp+28h+arg_10]
0x10040ae0a  add     rsp, 20h
0x10040ae0e  pop     rdi
0x10040ae0f  retn
0x10040ae10  cmp     qword ptr [rbx+60h], 0
0x10040ae15  jnz     short loc_10040ADF8
0x10040ae17  cmp     qword ptr [rbx+70h], 0
0x10040ae1c  jnz     short loc_10040AE39
0x10040ae1e  test    bpl, bpl
0x10040ae21  jz      short loc_10040ADF8
0x10040ae23  mov     ecx, 0C00CEE49h; int
0x10040ae28  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040ae2d  int     3; Trap to Debugger
0x10040ae2e  mov     ecx, 0C00CEE47h; int
0x10040ae33  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040ae38  int     3; Trap to Debugger
0x10040ae39  mov     ecx, 0C00CEE48h; int
0x10040ae3e  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
