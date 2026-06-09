# SclRegGetCanonicalMountKeyPath

- ea: `0x180009374`
- end: `0x180009430`
- name: `SclRegGetCanonicalMountKeyPath`
- size: `188`
- prototype: `__int64 __fastcall(__int64, wchar_t **)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180004844`
- `0x18000b738`
- `0x18000c73c`
- `0x18000deec`

## callees

- `0x180009374`
- `0x180014c48`
- `0x1800151f0`
- `0x180016e50`
- `0x1800179e0`

## string_xrefs

- `0x1800093c0`: `\REGISTRY\MACHINE`

## pseudocode

```c
__int64 __fastcall SclRegGetCanonicalMountKeyPath(__int64 a1, wchar_t **a2)
{
  ULONG v3; // ebx
  wchar_t *v4; // rax
  signed int LastErrorValue; // ecx
  struct _TEB *v6; // rax
  wchar_t v8[784]; // [rsp+20h] [rbp-638h] BYREF

  if ( (int)GetLoadedHiveKeyName(a1, v8) >= 0 || (int)GenerateRandomChars(v8) >= 0 )
  {
    v3 = 0;
    v4 = BuildPath(L"\\REGISTRY\\MACHINE", v8);
    *a2 = v4;
    if ( !v4 )
    {
      LastErrorValue = NtCurrentTeb()->LastErrorValue;
      v6 = NtCurrentTeb();
      if ( !LastErrorValue )
        LastErrorValue = 31;
      v3 = v6->LastErrorValue;
      if ( LastErrorValue > 0 )
      {
        if ( !v3 )
          LOWORD(v3) = 31;
        return (unsigned __int16)v3 | 0xC0070000;
      }
      else if ( !v3 )
      {
        return 31;
      }
    }
  }
  else
  {
    return (ULONG)-1073741823;
  }
  return v3;
}

```

## disassembly

```asm
0x180009374  mov     [rsp+arg_10], rbx
0x180009379  push    rdi
0x18000937a  sub     rsp, 650h
0x180009381  mov     rax, cs:__security_cookie
0x180009388  xor     rax, rsp
0x18000938b  mov     [rsp+658h+var_18], rax
0x180009393  mov     rdi, rdx
0x180009396  lea     rdx, [rsp+658h+var_638]
0x18000939b  call    GetLoadedHiveKeyName
0x1800093a0  test    eax, eax
0x1800093a2  jns     short loc_1800093B9
0x1800093a4  lea     rcx, [rsp+658h+var_638]
0x1800093a9  call    GenerateRandomChars
0x1800093ae  test    eax, eax
0x1800093b0  jns     short loc_1800093B9
0x1800093b2  mov     ebx, 0C0000001h
0x1800093b7  jmp     short loc_18000940D
0x1800093b9  lea     rdx, [rsp+658h+var_638]; STRSAFE_PCNZWCH
0x1800093be  xor     ebx, ebx
0x1800093c0  lea     rcx, aRegistryMachin_1; "\\REGISTRY\\MACHINE"
0x1800093c7  call    BuildPath
0x1800093cc  mov     [rdi], rax
0x1800093cf  test    rax, rax
0x1800093d2  jnz     short loc_18000940D
0x1800093d4  mov     rax, gs:30h
0x1800093dd  lea     edx, [rbx+1Fh]
0x1800093e0  mov     ecx, [rax+68h]
0x1800093e3  test    ecx, ecx
0x1800093e5  mov     rax, gs:30h
0x1800093ee  cmovz   ecx, edx
0x1800093f1  mov     ebx, [rax+68h]
0x1800093f4  test    ecx, ecx
0x1800093f6  jg      short loc_1800093FF
0x1800093f8  test    ebx, ebx
0x1800093fa  cmovz   ebx, edx
0x1800093fd  jmp     short loc_18000940D
0x1800093ff  test    ebx, ebx
0x180009401  cmovz   ebx, edx
0x180009404  movzx   ebx, bx
0x180009407  or      ebx, 0C0070000h
0x18000940d  mov     eax, ebx
0x18000940f  mov     rcx, [rsp+658h+var_18]
0x180009417  xor     rcx, rsp; StackCookie
0x18000941a  call    __security_check_cookie
0x18000941f  mov     rbx, [rsp+658h+arg_10]
0x180009427  add     rsp, 650h
0x18000942e  pop     rdi
0x18000942f  retn
```
