# SspGetTokenUser

- ea: `0x1800328a0`
- end: `0x1800329fc`
- name: `SspGetTokenUser`
- size: `348`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18002bd34`

## callees

- `0x1800061a0`
- `0x180009770`
- `0x18001a394`
- `0x18002c920`
- `0x1800328a0`
- `0x180032ec8`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18003290c`
- `ntdll!NtQueryInformationToken` at `0x180032971`
- `ntdll!NtQueryInformationToken` at `0x18003290c`
- `ntdll!NtQueryInformationToken` at `0x180032971`

## pseudocode

```c
__int64 __fastcall SspGetTokenUser(HANDLE TokenHandle, _QWORD *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  PVOID *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  void *Memory; // rsi
  ULONG TokenInformationLength; // [rsp+60h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      85,
      &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids,
      TokenHandle,
      a2);
  v4 = NtQueryInformationToken(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  v5 = v4;
  if ( v4 == -1073741789 )
  {
    Memory = (void *)DigestAllocateMemory(TokenInformationLength);
    if ( Memory )
    {
      v5 = NtQueryInformationToken(TokenHandle, TokenUser, Memory, TokenInformationLength, &TokenInformationLength);
      if ( (v5 & 0x80000000) != 0 )
      {
        DigestFreeMemory(Memory);
        v6 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v5;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_17;
        v7 = 87;
        v8 = v5;
        goto LABEL_15;
      }
      *a2 = Memory;
    }
    else
    {
      v5 = -1073741670;
    }
LABEL_16:
    v6 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_17;
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = 86;
    v8 = v4;
LABEL_15:
    WPP_SF_Lq(v6[2], v7, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, v8, TokenHandle);
    goto LABEL_16;
  }
LABEL_17:
  if ( v6 != &WPP_GLOBAL_Control && *((char *)v6 + 28) < 0 )
    WPP_SF_qD(v6[2], 88, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, TokenHandle, v5);
  return v5;
}

```

## disassembly

```asm
0x1800328a0  mov     rax, rsp
0x1800328a3  mov     [rax+8], rbx
0x1800328a7  mov     [rax+10h], rbp
0x1800328ab  push    rsi
0x1800328ac  push    rdi
0x1800328ad  push    r14
0x1800328af  sub     rsp, 30h
0x1800328b3  mov     r14, rdx
0x1800328b6  mov     dword ptr [rax+18h], 0
0x1800328bd  mov     rdi, rcx
0x1800328c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800328c7  lea     rbp, WPP_GLOBAL_Control
0x1800328ce  cmp     rcx, rbp
0x1800328d1  jz      short loc_1800328F5
0x1800328d3  test    byte ptr [rcx+1Ch], 80h
0x1800328d7  jz      short loc_1800328F5
0x1800328d9  mov     rcx, [rcx+10h]
0x1800328dd  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x1800328e4  mov     edx, 55h ; 'U'
0x1800328e9  mov     [rax-28h], r14
0x1800328ed  mov     r9, rdi
0x1800328f0  call    WPP_SF_qq
0x1800328f5  xor     r9d, r9d; TokenInformationLength
0x1800328f8  lea     rax, [rsp+48h+TokenInformationLength]
0x1800328fd  xor     r8d, r8d; TokenInformation
0x180032900  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180032905  mov     rcx, rdi; TokenHandle
0x180032908  lea     edx, [r9+1]; TokenInformationClass
0x18003290c  call    cs:__imp_NtQueryInformationToken
0x180032912  mov     ebx, eax
0x180032914  cmp     eax, 0C0000023h
0x180032919  jz      short loc_18003293F
0x18003291b  mov     rcx, cs:WPP_GLOBAL_Control
0x180032922  cmp     rcx, rbp
0x180032925  jz      loc_1800329E7
0x18003292b  test    byte ptr [rcx+1Ch], 1
0x18003292f  jz      loc_1800329C0
0x180032935  mov     edx, 56h ; 'V'
0x18003293a  mov     r9d, eax
0x18003293d  jmp     short loc_1800329A4
0x18003293f  mov     ecx, [rsp+48h+TokenInformationLength]; Size
0x180032943  call    DigestAllocateMemory
0x180032948  mov     rsi, rax
0x18003294b  test    rax, rax
0x18003294e  jnz     short loc_180032957
0x180032950  mov     ebx, 0C000009Ah
0x180032955  jmp     short loc_1800329B9
0x180032957  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18003295c  lea     rax, [rsp+48h+TokenInformationLength]
0x180032961  mov     r8, rsi; TokenInformation
0x180032964  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180032969  mov     edx, 1; TokenInformationClass
0x18003296e  mov     rcx, rdi; TokenHandle
0x180032971  call    cs:__imp_NtQueryInformationToken
0x180032977  mov     ebx, eax
0x180032979  test    eax, eax
0x18003297b  js      short loc_180032982
0x18003297d  mov     [r14], rsi
0x180032980  jmp     short loc_1800329B9
0x180032982  mov     rcx, rsi; hMem
0x180032985  call    DigestFreeMemory
0x18003298a  mov     rcx, cs:WPP_GLOBAL_Control
0x180032991  cmp     rcx, rbp
0x180032994  jz      short loc_1800329E7
0x180032996  test    byte ptr [rcx+1Ch], 1
0x18003299a  jz      short loc_1800329C0
0x18003299c  mov     edx, 57h ; 'W'
0x1800329a1  mov     r9d, ebx
0x1800329a4  mov     rcx, [rcx+10h]
0x1800329a8  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x1800329af  mov     [rsp+48h+ReturnLength], rdi
0x1800329b4  call    WPP_SF_Lq
0x1800329b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800329c0  cmp     rcx, rbp
0x1800329c3  jz      short loc_1800329E7
0x1800329c5  test    byte ptr [rcx+1Ch], 80h
0x1800329c9  jz      short loc_1800329E7
0x1800329cb  mov     rcx, [rcx+10h]
0x1800329cf  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x1800329d6  mov     edx, 58h ; 'X'
0x1800329db  mov     dword ptr [rsp+48h+ReturnLength], ebx
0x1800329df  mov     r9, rdi
0x1800329e2  call    WPP_SF_qD
0x1800329e7  mov     rbp, [rsp+48h+arg_8]
0x1800329ec  mov     eax, ebx
0x1800329ee  mov     rbx, [rsp+48h+arg_0]
0x1800329f3  add     rsp, 30h
0x1800329f7  pop     r14
0x1800329f9  pop     rdi
0x1800329fa  pop     rsi
0x1800329fb  retn
```
