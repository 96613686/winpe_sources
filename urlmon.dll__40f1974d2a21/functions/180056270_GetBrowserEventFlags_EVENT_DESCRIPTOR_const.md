# GetBrowserEventFlags(_EVENT_DESCRIPTOR const *)

- ea: `0x180056270`
- end: `0x180056374`
- name: `?GetBrowserEventFlags@@YAKPEBU_EVENT_DESCRIPTOR@@@Z`
- size: `260`
- prototype: `unsigned int __fastcall(const struct _EVENT_DESCRIPTOR *)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180055c2c`
- `0x180055d30`
- `0x180055e24`
- `0x180055f38`
- `0x180056034`
- `0x18005617c`

## callees

- `0x180056270`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180056306`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180056306`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x1800562f5`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x1800562f5`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x180056330`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x18005635c`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x180056330`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x18005635c`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005629c`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800562eb`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180056326`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005629c`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800562eb`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180056326`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1800562de`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1800562de`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x18005633b`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x18005633b`

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
    if ( dword_18015A4CC != 2 )
    {
      LOBYTE(v1) = dword_18015A4CC == 1;
      goto LABEL_5;
    }
    DWORD = IEConfiguration_GetDWORD(268435501);
    if ( (unsigned __int8)IEConfiguration_GetBool(536870914) || DWORD != 2 )
    {
      if ( LCIEIsCurrentProcessInPrivateOverrideSet() )
      {
        v1 = LCIEIsCurrentProcessInPrivate();
        if ( DWORD != 3 )
          dword_18015A4CC = v1;
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
0x180056270  mov     [rsp+arg_0], rcx
0x180056275  sub     rsp, 28h
0x180056279  mov     ecx, cs:_tls_index
0x18005627f  mov     rax, gs:58h
0x180056288  mov     edx, 8
0x18005628d  mov     rax, [rax+rcx*8]
0x180056291  cmp     byte ptr [rdx+rax], 0
0x180056295  jnz     short loc_1800562D2
0x180056297  mov     ecx, 20000019h
0x18005629c  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800562a2  test    al, al
0x1800562a4  jz      loc_18005636A
0x1800562aa  mov     eax, cs:dword_18015A4CC
0x1800562b0  mov     [rsp+28h+var_8], rbx
0x1800562b5  mov     byte ptr [rsp+28h+arg_0], 1
0x1800562ba  cmp     eax, 2
0x1800562bd  jz      short loc_1800562D9
0x1800562bf  cmp     eax, 1
0x1800562c2  setz    cl
0x1800562c5  mov     rbx, [rsp+28h+var_8]
0x1800562ca  test    cl, cl
0x1800562cc  jnz     loc_18005636A
0x1800562d2  xor     eax, eax
0x1800562d4  add     rsp, 28h
0x1800562d8  retn
0x1800562d9  mov     ecx, 1000002Dh
0x1800562de  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x1800562e4  mov     ecx, 20000002h
0x1800562e9  mov     ebx, eax
0x1800562eb  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800562f1  test    al, al
0x1800562f3  jz      short loc_18005631C
0x1800562f5  call    cs:__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ; LCIEIsCurrentProcessInPrivateOverrideSet(void)
0x1800562fb  test    al, al
0x1800562fd  jnz     short loc_180056306
0x1800562ff  movzx   ecx, byte ptr [rsp+28h+arg_0]
0x180056304  jmp     short loc_1800562C5
0x180056306  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x18005630c  movzx   ecx, al
0x18005630f  cmp     ebx, 3
0x180056312  jz      short loc_1800562C5
0x180056314  mov     cs:dword_18015A4CC, ecx
0x18005631a  jmp     short loc_1800562C5
0x18005631c  cmp     ebx, 2
0x18005631f  jnz     short loc_1800562F5
0x180056321  mov     ecx, 10000038h
0x180056326  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18005632c  test    al, al
0x18005632e  jz      short loc_18005633B
0x180056330  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x180056336  movzx   ecx, al
0x180056339  jmp     short loc_1800562C5
0x18005633b  call    cs:__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ; GetEdgeBrowsingEnvironment(void)
0x180056341  mov     r8, rax
0x180056344  lea     rdx, [rsp+28h+arg_0]
0x180056349  mov     rcx, [rax]
0x18005634c  mov     rax, [rcx+78h]
0x180056350  mov     rcx, r8
0x180056353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056358  test    eax, eax
0x18005635a  jns     short loc_1800562FF
0x18005635c  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x180056362  movzx   ecx, al
0x180056365  jmp     loc_1800562C5
0x18005636a  mov     eax, 2
0x18005636f  jmp     loc_1800562D4
```
