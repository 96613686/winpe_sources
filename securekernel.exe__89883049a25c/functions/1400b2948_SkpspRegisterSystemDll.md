# SkpspRegisterSystemDll

- ea: `0x1400b2948`
- end: `0x1400b2a9d`
- name: `SkpspRegisterSystemDll`
- size: `341`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x140014dd0`

## callees

- `0x140002ef0`
- `0x14000e460`
- `0x14001e2c4`
- `0x140023ee8`
- `0x140060370`
- `0x1400603cc`
- `0x140063578`
- `0x140063694`
- `0x1400b2948`
- `0x1400b2aa4`

## pseudocode

```c
__int64 __fastcall SkpspRegisterSystemDll(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 result; // rax
  __int64 v7; // rax
  __int64 v8; // rdi
  __int64 v9; // r12
  int SecureImageInfo; // ebx
  __int64 v11; // rax
  __int64 v12; // rbp
  unsigned int v13; // r15d
  int v14; // r13d
  int v15; // eax
  __int128 v16; // [rsp+30h] [rbp-68h] BYREF
  __int128 v17; // [rsp+40h] [rbp-58h]
  __int64 v18; // [rsp+B8h] [rbp+20h] BYREF

  v18 = 0;
  v16 = 0;
  v17 = 0;
  result = SkmmGetNtSecureImage(0, a1, 0, &v18);
  if ( (int)result >= 0 )
  {
    v7 = SkiAttachProcess(PsIumSystemProcess);
    v8 = v18;
    v9 = v7;
    SecureImageInfo = SkmmGetSecureImageInfo(v18, &v16);
    if ( SecureImageInfo >= 0 )
    {
      if ( BYTE13(v17) )
      {
        v11 = v17;
        v12 = v16;
        *(_QWORD *)(a2 + 16) = a1;
        v13 = DWORD2(v17);
        *(_QWORD *)(a2 + 24) = v12;
        *(_QWORD *)(a2 + 40) = v11;
        *(_DWORD *)(a2 + 32) = v13;
        v14 = PsIumSystemProcess;
        SecureImageInfo = SkmiLockImageShared(v8);
        if ( SecureImageInfo >= 0 )
        {
          v15 = SkmiMapImageInProcess(v14, v8, v12, 0, *(_DWORD *)(v8 + 4), 0);
          _InterlockedDecrement((volatile signed __int32 *)(v8 + 136));
          SecureImageInfo = v15;
          if ( v15 >= 0 )
          {
            SecureImageInfo = SkpspResolveSystemDllsExports(a2, v12, v13);
            if ( SecureImageInfo >= 0 )
            {
              if ( (char ***)a2 != &SkpspNativeDllInfo
                || (SecureImageInfo = SkmmInitializeUserScpPages(), SecureImageInfo >= 0) )
              {
                SecureImageInfo = 0;
              }
            }
            SkmiUnmapViewOfSection(v12, 0, 2);
          }
        }
      }
      else
      {
        SecureImageInfo = -1073741701;
      }
    }
    SkiAttachProcess(v9);
    if ( a3 && SecureImageInfo >= 0 )
      *a3 = v8;
    else
      SkobDereferenceObject(v8);
    return (unsigned int)SecureImageInfo;
  }
  return result;
}

```

## disassembly

```asm
0x1400b2948  mov     rax, rsp
0x1400b294b  push    rbx
0x1400b294c  push    rbp
0x1400b294d  push    rsi
0x1400b294e  push    rdi
0x1400b294f  push    r12
0x1400b2951  push    r13
0x1400b2953  push    r14
0x1400b2955  push    r15
0x1400b2957  sub     rsp, 58h
0x1400b295b  xorps   xmm0, xmm0
0x1400b295e  mov     qword ptr [rax+20h], 0
0x1400b2966  mov     rsi, rdx
0x1400b2969  lea     r9, [rax+20h]
0x1400b296d  mov     rdx, rcx
0x1400b2970  mov     r14, r8
0x1400b2973  mov     r15, rcx
0x1400b2976  xor     r8d, r8d
0x1400b2979  xor     ecx, ecx
0x1400b297b  movups  xmmword ptr [rax-68h], xmm0
0x1400b297f  movups  xmmword ptr [rax-58h], xmm0
0x1400b2983  call    SkmmGetNtSecureImage
0x1400b2988  test    eax, eax
0x1400b298a  js      loc_1400B2A8B
0x1400b2990  mov     rcx, cs:PsIumSystemProcess
0x1400b2997  call    SkiAttachProcess
0x1400b299c  mov     rdi, [rsp+98h+arg_18]
0x1400b29a4  lea     rdx, [rsp+98h+var_68]
0x1400b29a9  mov     rcx, rdi
0x1400b29ac  mov     r12, rax
0x1400b29af  call    SkmmGetSecureImageInfo
0x1400b29b4  mov     ebx, eax
0x1400b29b6  test    eax, eax
0x1400b29b8  js      loc_1400B2A6B
0x1400b29be  cmp     [rsp+98h+var_4B], 0
0x1400b29c3  jnz     short loc_1400B29CF
0x1400b29c5  mov     ebx, 0C000007Bh
0x1400b29ca  jmp     loc_1400B2A6B
0x1400b29cf  mov     rax, [rsp+98h+var_58]
0x1400b29d4  mov     rcx, rdi
0x1400b29d7  mov     rbp, qword ptr [rsp+98h+var_68]
0x1400b29dc  mov     [rsi+10h], r15
0x1400b29e0  mov     r15d, [rsp+98h+var_50]
0x1400b29e5  mov     [rsi+18h], rbp
0x1400b29e9  mov     [rsi+28h], rax
0x1400b29ed  mov     [rsi+20h], r15d
0x1400b29f1  mov     r13, cs:PsIumSystemProcess
0x1400b29f8  call    SkmiLockImageShared
0x1400b29fd  mov     ebx, eax
0x1400b29ff  test    eax, eax
0x1400b2a01  js      short loc_1400B2A6B
0x1400b2a03  mov     eax, [rdi+4]
0x1400b2a06  xor     r9d, r9d
0x1400b2a09  mov     [rsp+98h+var_70], 0
0x1400b2a11  mov     r8, rbp
0x1400b2a14  mov     rdx, rdi
0x1400b2a17  mov     [rsp+98h+var_78], eax
0x1400b2a1b  mov     rcx, r13
0x1400b2a1e  call    SkmiMapImageInProcess
0x1400b2a23  lock dec dword ptr [rdi+88h]
0x1400b2a2a  mov     ebx, eax
0x1400b2a2c  test    eax, eax
0x1400b2a2e  js      short loc_1400B2A6B
0x1400b2a30  mov     r8d, r15d
0x1400b2a33  mov     rdx, rbp
0x1400b2a36  mov     rcx, rsi
0x1400b2a39  call    SkpspResolveSystemDllsExports
0x1400b2a3e  mov     ebx, eax
0x1400b2a40  test    eax, eax
0x1400b2a42  js      short loc_1400B2A5D
0x1400b2a44  lea     rax, SkpspNativeDllInfo
0x1400b2a4b  cmp     rsi, rax
0x1400b2a4e  jnz     short loc_1400B2A5B
0x1400b2a50  call    SkmmInitializeUserScpPages
0x1400b2a55  mov     ebx, eax
0x1400b2a57  test    eax, eax
0x1400b2a59  js      short loc_1400B2A5D
0x1400b2a5b  xor     ebx, ebx
0x1400b2a5d  xor     edx, edx
0x1400b2a5f  mov     rcx, rbp
0x1400b2a62  lea     r8d, [rdx+2]
0x1400b2a66  call    SkmiUnmapViewOfSection
0x1400b2a6b  mov     rcx, r12
0x1400b2a6e  call    SkiAttachProcess
0x1400b2a73  test    r14, r14
0x1400b2a76  jz      short loc_1400B2A81
0x1400b2a78  test    ebx, ebx
0x1400b2a7a  js      short loc_1400B2A81
0x1400b2a7c  mov     [r14], rdi
0x1400b2a7f  jmp     short loc_1400B2A89
0x1400b2a81  mov     rcx, rdi
0x1400b2a84  call    SkobDereferenceObject
0x1400b2a89  mov     eax, ebx
0x1400b2a8b  add     rsp, 58h
0x1400b2a8f  pop     r15
0x1400b2a91  pop     r14
0x1400b2a93  pop     r13
0x1400b2a95  pop     r12
0x1400b2a97  pop     rdi
0x1400b2a98  pop     rsi
0x1400b2a99  pop     rbp
0x1400b2a9a  pop     rbx
0x1400b2a9b  retn
```
