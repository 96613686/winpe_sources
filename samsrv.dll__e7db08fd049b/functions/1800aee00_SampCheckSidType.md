# SampCheckSidType

- ea: `0x1800aee00`
- end: `0x1800aefd2`
- name: `SampCheckSidType`
- size: `466`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, int, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800af690`

## callees

- `0x180021460`
- `0x180027e24`
- `0x1800ac31c`
- `0x1800ac74c`
- `0x1800aee00`

## import_xrefs

- `ntdll!RtlValidSid` at `0x1800aee6d`
- `ntdll!RtlValidSid` at `0x1800aee6d`
- `ntdll!RtlLengthSid` at `0x1800aee82`
- `ntdll!RtlLengthSid` at `0x1800aee82`
- `ntdll!RtlEqualSid` at `0x1800aeefc`
- `ntdll!RtlEqualSid` at `0x1800aef0d`
- `ntdll!RtlEqualSid` at `0x1800aef43`
- `ntdll!RtlEqualSid` at `0x1800aef54`
- `ntdll!RtlEqualSid` at `0x1800aeefc`
- `ntdll!RtlEqualSid` at `0x1800aef0d`
- `ntdll!RtlEqualSid` at `0x1800aef43`
- `ntdll!RtlEqualSid` at `0x1800aef54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aef89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aef89`

## pseudocode

```c
__int64 __fastcall SampCheckSidType(
        void *Src,
        char a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        _BYTE *a7,
        _BYTE *a8,
        _BYTE *a9,
        _BYTE *a10,
        _BYTE *a11)
{
  unsigned int v11; // ebp
  int v14; // ebx
  unsigned int v15; // ebp

  v11 = 0;
  *a7 = 0;
  *a8 = 0;
  *a9 = 0;
  *a10 = 0;
  *a11 = 0;
  if ( Src && RtlValidSid(Src) && (!a2 || RtlLengthSid(Src) <= 0x1C) )
  {
    v14 = 0;
    if ( SampIsWellKnownSid(Src) )
    {
      *a7 = 1;
    }
    else if ( SampIsMemberOfBuiltinDomain(Src) )
    {
      *a8 = 1;
    }
    else
    {
      v14 = SampSplitSid(Src);
      if ( v14 >= 0 )
      {
        while ( v11 < a3 )
        {
          if ( RtlEqualSid(0, *(PSID *)(a4 + 8LL * v11)) || RtlEqualSid(Src, *(PSID *)(a4 + 8LL * v11)) )
          {
            *a9 = 1;
            break;
          }
          ++v11;
        }
        v15 = 0;
        if ( !*a9 )
        {
          while ( v15 < a5 )
          {
            if ( RtlEqualSid(0, *(PSID *)(a6 + 8LL * v15)) || RtlEqualSid(Src, *(PSID *)(a6 + 8LL * v15)) )
            {
              *a11 = 1;
              break;
            }
            ++v15;
          }
          if ( !*a11 )
            *a10 = 1;
        }
      }
    }
  }
  else
  {
    v14 = -1073741811;
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      205,
      WPP_48bf36016493398285a8dbc678e80a21_Traceguids,
      (unsigned int)v14,
      v14);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800aee00  mov     rax, rsp
0x1800aee03  mov     [rax+10h], rbx
0x1800aee07  mov     [rax+20h], r9
0x1800aee0b  mov     [rax+18h], r8d
0x1800aee0f  push    rbp
0x1800aee10  push    rsi
0x1800aee11  push    rdi
0x1800aee12  push    r12
0x1800aee14  push    r13
0x1800aee16  push    r14
0x1800aee18  push    r15
0x1800aee1a  sub     rsp, 30h
0x1800aee1e  mov     r14, [rsp+68h+arg_30]
0x1800aee26  xor     ebp, ebp
0x1800aee28  mov     r15, [rsp+68h+arg_38]
0x1800aee30  mov     bl, dl
0x1800aee32  mov     r12, [rsp+68h+arg_40]
0x1800aee3a  mov     rsi, rcx
0x1800aee3d  mov     r13, [rsp+68h+arg_50]
0x1800aee45  mov     edi, ebp
0x1800aee47  mov     [r14], bpl
0x1800aee4a  mov     [r15], bpl
0x1800aee4d  mov     [r12], bpl
0x1800aee51  mov     [rax+8], rbp
0x1800aee55  mov     rax, [rsp+68h+arg_48]
0x1800aee5d  mov     [rax], bpl
0x1800aee60  mov     [r13+0], bpl
0x1800aee64  test    rcx, rcx
0x1800aee67  jz      loc_1800AEF7C
0x1800aee6d  call    cs:__imp_RtlValidSid
0x1800aee73  test    al, al
0x1800aee75  jz      loc_1800AEF7C
0x1800aee7b  test    bl, bl
0x1800aee7d  jz      short loc_1800AEE91
0x1800aee7f  mov     rcx, rsi; Sid
0x1800aee82  call    cs:__imp_RtlLengthSid
0x1800aee88  cmp     eax, 1Ch
0x1800aee8b  ja      loc_1800AEF7C
0x1800aee91  mov     rcx, rsi; Sid
0x1800aee94  mov     ebx, ebp
0x1800aee96  call    ?SampIsWellKnownSid@@YAEPEAX@Z; SampIsWellKnownSid(void *)
0x1800aee9b  test    al, al
0x1800aee9d  jz      short loc_1800AEEA8
0x1800aee9f  mov     byte ptr [r14], 1
0x1800aeea3  jmp     loc_1800AEF8F
0x1800aeea8  mov     rcx, rsi; Sid
0x1800aeeab  call    ?SampIsMemberOfBuiltinDomain@@YAEPEAX@Z; SampIsMemberOfBuiltinDomain(void *)
0x1800aeeb0  test    al, al
0x1800aeeb2  jz      short loc_1800AEEBD
0x1800aeeb4  mov     byte ptr [r15], 1
0x1800aeeb8  jmp     loc_1800AEF8F
0x1800aeebd  lea     r8, [rsp+68h+arg_30]
0x1800aeec5  mov     rcx, rsi; Src
0x1800aeec8  lea     rdx, [rsp+68h+Sid1]
0x1800aeecd  call    SampSplitSid
0x1800aeed2  mov     rdi, [rsp+68h+Sid1]
0x1800aeed7  mov     ebx, eax
0x1800aeed9  test    eax, eax
0x1800aeedb  js      loc_1800AEF81
0x1800aeee1  mov     r15, [rsp+68h+arg_18]
0x1800aeee9  cmp     ebp, [rsp+68h+arg_10]
0x1800aeef0  jnb     short loc_1800AEF20
0x1800aeef2  mov     r14d, ebp
0x1800aeef5  mov     rcx, rdi; Sid1
0x1800aeef8  mov     rdx, [r15+r14*8]; Sid2
0x1800aeefc  call    cs:__imp_RtlEqualSid
0x1800aef02  test    al, al
0x1800aef04  jnz     short loc_1800AEF1B
0x1800aef06  mov     rdx, [r15+r14*8]; Sid2
0x1800aef0a  mov     rcx, rsi; Sid1
0x1800aef0d  call    cs:__imp_RtlEqualSid
0x1800aef13  test    al, al
0x1800aef15  jnz     short loc_1800AEF1B
0x1800aef17  inc     ebp
0x1800aef19  jmp     short loc_1800AEEE9
0x1800aef1b  mov     byte ptr [r12], 1
0x1800aef20  xor     ebp, ebp
0x1800aef22  cmp     [r12], bpl
0x1800aef26  jnz     short loc_1800AEF81
0x1800aef28  mov     r14, [rsp+68h+arg_28]
0x1800aef30  cmp     ebp, [rsp+68h+arg_20]
0x1800aef37  jnb     short loc_1800AEF67
0x1800aef39  mov     r15d, ebp
0x1800aef3c  mov     rcx, rdi; Sid1
0x1800aef3f  mov     rdx, [r14+r15*8]; Sid2
0x1800aef43  call    cs:__imp_RtlEqualSid
0x1800aef49  test    al, al
0x1800aef4b  jnz     short loc_1800AEF62
0x1800aef4d  mov     rdx, [r14+r15*8]; Sid2
0x1800aef51  mov     rcx, rsi; Sid1
0x1800aef54  call    cs:__imp_RtlEqualSid
0x1800aef5a  test    al, al
0x1800aef5c  jnz     short loc_1800AEF62
0x1800aef5e  inc     ebp
0x1800aef60  jmp     short loc_1800AEF30
0x1800aef62  mov     byte ptr [r13+0], 1
0x1800aef67  xor     ebp, ebp
0x1800aef69  cmp     [r13+0], bpl
0x1800aef6d  jnz     short loc_1800AEF81
0x1800aef6f  mov     rax, [rsp+68h+arg_48]
0x1800aef77  mov     byte ptr [rax], 1
0x1800aef7a  jmp     short loc_1800AEF81
0x1800aef7c  mov     ebx, 0C000000Dh
0x1800aef81  test    rdi, rdi
0x1800aef84  jz      short loc_1800AEF8F
0x1800aef86  mov     rcx, rdi; hMem
0x1800aef89  call    cs:__imp_LocalFree
0x1800aef8f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aef96  test    dword ptr [rcx+44h], 20000h
0x1800aef9d  jz      short loc_1800AEFBB
0x1800aef9f  mov     rcx, [rcx+38h]
0x1800aefa3  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x1800aefaa  mov     edx, 0CDh
0x1800aefaf  mov     [rsp+68h+var_48], ebx
0x1800aefb3  mov     r9d, ebx
0x1800aefb6  call    WPP_SF_Dd
0x1800aefbb  mov     eax, ebx
0x1800aefbd  mov     rbx, [rsp+68h+arg_8]
0x1800aefc2  add     rsp, 30h
0x1800aefc6  pop     r15
0x1800aefc8  pop     r14
0x1800aefca  pop     r13
0x1800aefcc  pop     r12
0x1800aefce  pop     rdi
0x1800aefcf  pop     rsi
0x1800aefd0  pop     rbp
0x1800aefd1  retn
```
