# GetBrowserEventFlags(_EVENT_DESCRIPTOR const *)

- ea: `0x180058ea0`
- end: `0x180058fde`
- name: `?GetBrowserEventFlags@@YAKPEBU_EVENT_DESCRIPTOR@@@Z`
- size: `318`
- prototype: `unsigned int __fastcall(const struct _EVENT_DESCRIPTOR *)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005883c`
- `0x180058944`
- `0x180058a3c`
- `0x180058b54`
- `0x180058c58`
- `0x180058da4`

## callees

- `0x180058ea0`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180058f4f`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180058f4f`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x180058f38`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x180058f38`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x180058f85`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x180058fc0`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x180058f85`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x180058fc0`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180058ecc`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180058f28`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180058f75`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180058ecc`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180058f28`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180058f75`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180058f15`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180058f15`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x180058f99`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x180058f99`

## pseudocode

```c
__int64 __fastcall GetBrowserEventFlags(const struct _EVENT_DESCRIPTOR *a1)
{
  BOOL v1; // ecx
  int DWORD; // ebx
  struct IEdgeBrowsingEnvironment *EdgeBrowsingEnvironment; // rax
  const struct _EVENT_DESCRIPTOR *v5; // [rsp+30h] [rbp+8h] BYREF

  v5 = a1;
  if ( *(_BYTE *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 8LL) )
    return 0;
  if ( (unsigned __int8)IEConfiguration_GetBool(536870937) )
  {
    LOBYTE(v5) = 1;
    if ( dword_1801675C4 != 2 )
    {
      LOBYTE(v1) = dword_1801675C4 == 1;
      goto LABEL_5;
    }
    DWORD = IEConfiguration_GetDWORD(268435501);
    if ( (unsigned __int8)IEConfiguration_GetBool(536870914) || DWORD != 2 )
    {
      if ( LCIEIsCurrentProcessInPrivateOverrideSet() )
      {
        v1 = LCIEIsCurrentProcessInPrivate();
        if ( DWORD != 3 )
          dword_1801675C4 = v1;
LABEL_5:
        if ( !v1 )
          return 0;
        return 2;
      }
    }
    else if ( (unsigned __int8)IEConfiguration_GetBool(268435512)
           || (EdgeBrowsingEnvironment = GetEdgeBrowsingEnvironment(),
               (*(int (__fastcall **)(struct IEdgeBrowsingEnvironment *, const struct _EVENT_DESCRIPTOR **))(*(_QWORD *)EdgeBrowsingEnvironment + 120LL))(
                 EdgeBrowsingEnvironment,
                 &v5) < 0) )
    {
      LOBYTE(v1) = LCIEIsCurrentProcessUsingInPrivateComponents();
      goto LABEL_5;
    }
    LOBYTE(v1) = (_BYTE)v5;
    goto LABEL_5;
  }
  return 2;
}

```

## disassembly

```asm
0x180058ea0  mov     [rsp+arg_0], rcx
0x180058ea5  sub     rsp, 28h
0x180058ea9  mov     ecx, cs:_tls_index
0x180058eaf  mov     rax, gs:58h
0x180058eb8  mov     edx, 8
0x180058ebd  mov     rax, [rax+rcx*8]
0x180058ec1  cmp     byte ptr [rdx+rax], 0
0x180058ec5  jnz     short loc_180058F08
0x180058ec7  mov     ecx, 20000019h
0x180058ecc  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180058ed3  nop     dword ptr [rax+rax+00h]
0x180058ed8  test    al, al
0x180058eda  jz      loc_180058FD4
0x180058ee0  mov     eax, cs:dword_1801675C4
0x180058ee6  mov     [rsp+28h+var_8], rbx
0x180058eeb  mov     byte ptr [rsp+28h+arg_0], 1
0x180058ef0  cmp     eax, 2
0x180058ef3  jz      short loc_180058F10
0x180058ef5  cmp     eax, 1
0x180058ef8  setz    cl
0x180058efb  mov     rbx, [rsp+28h+var_8]
0x180058f00  test    cl, cl
0x180058f02  jnz     loc_180058FD4
0x180058f08  xor     eax, eax
0x180058f0a  add     rsp, 28h
0x180058f0e  retn
0x180058f10  mov     ecx, 1000002Dh
0x180058f15  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x180058f1c  nop     dword ptr [rax+rax+00h]
0x180058f21  mov     ecx, 20000002h
0x180058f26  mov     ebx, eax
0x180058f28  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180058f2f  nop     dword ptr [rax+rax+00h]
0x180058f34  test    al, al
0x180058f36  jz      short loc_180058F6B
0x180058f38  call    cs:__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ; LCIEIsCurrentProcessInPrivateOverrideSet(void)
0x180058f3f  nop     dword ptr [rax+rax+00h]
0x180058f44  test    al, al
0x180058f46  jnz     short loc_180058F4F
0x180058f48  movzx   ecx, byte ptr [rsp+28h+arg_0]
0x180058f4d  jmp     short loc_180058EFB
0x180058f4f  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x180058f56  nop     dword ptr [rax+rax+00h]
0x180058f5b  movzx   ecx, al
0x180058f5e  cmp     ebx, 3
0x180058f61  jz      short loc_180058EFB
0x180058f63  mov     cs:dword_1801675C4, ecx
0x180058f69  jmp     short loc_180058EFB
0x180058f6b  cmp     ebx, 2
0x180058f6e  jnz     short loc_180058F38
0x180058f70  mov     ecx, 10000038h
0x180058f75  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180058f7c  nop     dword ptr [rax+rax+00h]
0x180058f81  test    al, al
0x180058f83  jz      short loc_180058F99
0x180058f85  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x180058f8c  nop     dword ptr [rax+rax+00h]
0x180058f91  movzx   ecx, al
0x180058f94  jmp     loc_180058EFB
0x180058f99  call    cs:__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ; GetEdgeBrowsingEnvironment(void)
0x180058fa0  nop     dword ptr [rax+rax+00h]
0x180058fa5  mov     r8, rax
0x180058fa8  lea     rdx, [rsp+28h+arg_0]
0x180058fad  mov     rcx, [rax]
0x180058fb0  mov     rax, [rcx+78h]
0x180058fb4  mov     rcx, r8
0x180058fb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058fbc  test    eax, eax
0x180058fbe  jns     short loc_180058F48
0x180058fc0  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x180058fc7  nop     dword ptr [rax+rax+00h]
0x180058fcc  movzx   ecx, al
0x180058fcf  jmp     loc_180058EFB
0x180058fd4  mov     eax, 2
0x180058fd9  jmp     loc_180058F0A
```
