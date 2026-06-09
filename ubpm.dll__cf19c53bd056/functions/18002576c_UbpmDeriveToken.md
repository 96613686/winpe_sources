# UbpmDeriveToken

- ea: `0x18002576c`
- end: `0x1800258fc`
- name: `UbpmDeriveToken`
- size: `400`
- prototype: `__int64 __fastcall(HANDLE ExistingTokenHandle, int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180022054`

## callees

- `0x18002576c`
- `0x180025904`
- `0x180032e38`
- `0x1800347bc`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x1800257bc`
- `ntdll!NtQueryInformationToken` at `0x18002585b`
- `ntdll!NtQueryInformationToken` at `0x1800257bc`
- `ntdll!NtQueryInformationToken` at `0x18002585b`
- `ntdll!RtlNtStatusToDosError` at `0x180025818`
- `ntdll!RtlNtStatusToDosError` at `0x1800258b6`
- `ntdll!RtlNtStatusToDosError` at `0x180025818`
- `ntdll!RtlNtStatusToDosError` at `0x1800258b6`

## pseudocode

```c
__int64 __fastcall UbpmDeriveToken(HANDLE ExistingTokenHandle, int a2, void **a3)
{
  int v6; // eax
  int v7; // edi
  ULONG v8; // ebx
  NTSTATUS v10; // eax
  ULONG v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  _DWORD v14[10]; // [rsp+30h] [rbp-28h] BYREF
  int TokenInformation; // [rsp+70h] [rbp+18h] BYREF
  ULONG ReturnLength; // [rsp+78h] [rbp+20h] BYREF

  ReturnLength = 0;
  v14[0] = 0;
  TokenInformation = 1;
  *a3 = 0;
  v6 = NtQueryInformationToken(ExistingTokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength);
  if ( v6 < 0 )
    goto LABEL_18;
  if ( TokenInformation != 2 )
  {
    v7 = 0;
    if ( TokenInformation != 1 )
      goto LABEL_4;
    v6 = NtQueryInformationToken(ExistingTokenHandle, TokenElevation, v14, 4u, &ReturnLength);
    if ( v6 >= 0 )
    {
      if ( !v14[0] )
        goto LABEL_4;
      goto LABEL_14;
    }
LABEL_18:
    v11 = RtlNtStatusToDosError(v6);
    v8 = v11;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v8;
    v13 = 56;
LABEL_21:
    WPP_SF_d(v12[2], v13, WPP_134408c016563692a0776b6ad2359b4f_Traceguids, v11);
    return v8;
  }
LABEL_14:
  v7 = 1;
LABEL_4:
  v8 = 0;
  if ( a2 == 1 )
  {
    if ( v7 )
      return v8;
    v10 = LUAGetElevatedToken(ExistingTokenHandle, a3);
    if ( v10 >= 0 )
      return v8;
    v11 = RtlNtStatusToDosError(v10);
    v8 = v11;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v8;
    v13 = 57;
    goto LABEL_21;
  }
  if ( v7 == 1 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_134408c016563692a0776b6ad2359b4f_Traceguids);
  return v8;
}

```

## disassembly

```asm
0x18002576c  mov     rax, rsp
0x18002576f  mov     [rax+8], rbx
0x180025773  mov     [rax+10h], rbp
0x180025777  push    rsi
0x180025778  push    rdi
0x180025779  push    r14
0x18002577b  sub     rsp, 40h
0x18002577f  mov     ebx, 4
0x180025784  mov     dword ptr [rax+20h], 0
0x18002578b  mov     dword ptr [rax-28h], 0
0x180025792  mov     r14, r8
0x180025795  mov     dword ptr [rax+18h], 1
0x18002579c  lea     rax, [rax+20h]
0x1800257a0  mov     ebp, edx
0x1800257a2  mov     qword ptr [r8], 0
0x1800257a9  lea     edx, [rbx+0Eh]; TokenInformationClass
0x1800257ac  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800257b1  mov     r9d, ebx; TokenInformationLength
0x1800257b4  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x1800257b9  mov     rsi, rcx
0x1800257bc  call    cs:__imp_NtQueryInformationToken
0x1800257c2  test    eax, eax
0x1800257c4  js      loc_1800258B4
0x1800257ca  cmp     [rsp+58h+TokenInformation], 2
0x1800257cf  jz      loc_18002586F
0x1800257d5  xor     edi, edi
0x1800257d7  cmp     [rsp+58h+TokenInformation], 1
0x1800257dc  jz      short loc_180025841
0x1800257de  xor     ebx, ebx
0x1800257e0  cmp     ebp, 1
0x1800257e3  jz      short loc_180025803
0x1800257e5  cmp     edi, 1
0x1800257e8  jz      loc_180025879
0x1800257ee  mov     rbp, [rsp+58h+arg_8]
0x1800257f3  mov     eax, ebx
0x1800257f5  mov     rbx, [rsp+58h+arg_0]
0x1800257fa  add     rsp, 40h
0x1800257fe  pop     r14
0x180025800  pop     rdi
0x180025801  pop     rsi
0x180025802  retn
0x180025803  test    edi, edi
0x180025805  jnz     short loc_1800257EE
0x180025807  mov     rdx, r14; NewTokenHandle
0x18002580a  mov     rcx, rsi; ExistingTokenHandle
0x18002580d  call    LUAGetElevatedToken
0x180025812  test    eax, eax
0x180025814  jns     short loc_1800257EE
0x180025816  mov     ecx, eax; Status
0x180025818  call    cs:__imp_RtlNtStatusToDosError
0x18002581e  mov     ebx, eax
0x180025820  mov     rcx, cs:WPP_GLOBAL_Control
0x180025827  lea     rdx, WPP_GLOBAL_Control
0x18002582e  cmp     rcx, rdx
0x180025831  jz      short loc_1800257EE
0x180025833  test    byte ptr [rcx+1Ch], 1
0x180025837  jz      short loc_1800257EE
0x180025839  lea     edx, [rdi+39h]
0x18002583c  jmp     loc_1800258E4
0x180025841  lea     rax, [rsp+58h+arg_18]
0x180025846  mov     r9d, ebx; TokenInformationLength
0x180025849  lea     r8, [rsp+58h+var_28]; TokenInformation
0x18002584e  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180025853  mov     edx, 14h; TokenInformationClass
0x180025858  mov     rcx, rsi; TokenHandle
0x18002585b  call    cs:__imp_NtQueryInformationToken
0x180025861  test    eax, eax
0x180025863  js      short loc_1800258B4
0x180025865  cmp     [rsp+58h+var_28], edi
0x180025869  jz      loc_1800257DE
0x18002586f  mov     edi, 1
0x180025874  jmp     loc_1800257DE
0x180025879  mov     rcx, cs:WPP_GLOBAL_Control
0x180025880  lea     rdx, WPP_GLOBAL_Control
0x180025887  cmp     rcx, rdx
0x18002588a  jz      loc_1800257EE
0x180025890  test    byte ptr [rcx+1Ch], 2
0x180025894  jz      loc_1800257EE
0x18002589a  mov     rcx, [rcx+10h]
0x18002589e  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x1800258a5  mov     edx, 3Bh ; ';'
0x1800258aa  call    WPP_SF_
0x1800258af  jmp     loc_1800257EE
0x1800258b4  mov     ecx, eax; Status
0x1800258b6  call    cs:__imp_RtlNtStatusToDosError
0x1800258bc  mov     ebx, eax
0x1800258be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800258c5  lea     rdx, WPP_GLOBAL_Control
0x1800258cc  cmp     rcx, rdx
0x1800258cf  jz      loc_1800257EE
0x1800258d5  test    byte ptr [rcx+1Ch], 1
0x1800258d9  jz      loc_1800257EE
0x1800258df  mov     edx, 38h ; '8'
0x1800258e4  mov     rcx, [rcx+10h]
0x1800258e8  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x1800258ef  mov     r9d, eax
0x1800258f2  call    WPP_SF_d
0x1800258f7  jmp     loc_1800257EE
```
