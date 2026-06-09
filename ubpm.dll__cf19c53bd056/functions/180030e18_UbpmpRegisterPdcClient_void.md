# UbpmpRegisterPdcClient(void)

- ea: `0x180030e18`
- end: `0x180030ee9`
- name: `?UbpmpRegisterPdcClient@@YAXXZ`
- size: `209`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18002e220`

## callees

- `0x180030e18`
- `0x180032e38`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180030e38`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180030e38`
- `ntdll!RtlNtStatusToDosError` at `0x180030ebf`
- `ntdll!RtlNtStatusToDosError` at `0x180030ebf`
- `UMPDC!PdcTaskClientRegister` at `0x180030e9a`
- `UMPDC!PdcTaskClientRegister` at `0x180030e9a`
- `UMPDC!PdcActivationClientRegister` at `0x180030e86`
- `UMPDC!PdcActivationClientRegister` at `0x180030e86`

## pseudocode

```c
void UbpmpRegisterPdcClient(void)
{
  int v0; // ecx
  int v1; // ecx
  NTSTATUS v2; // eax
  ULONG v3; // eax
  int v4; // [rsp+30h] [rbp+8h] BYREF

  v0 = dword_18004CB34;
  v4 = 0;
  if ( !dword_18004CB34 )
  {
    RtlGetDeviceFamilyInfoEnum(0, &v4, 0);
    if ( v4 == 5 || (v0 = 1, (unsigned int)(v4 - 11) <= 1) )
      v0 = 2;
    dword_18004CB34 = v0;
  }
  if ( !qword_18004CB38 )
  {
    v1 = v0 - 1;
    if ( v1 )
    {
      if ( v1 != 1 )
      {
        v2 = -1073741637;
LABEL_13:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v3 = RtlNtStatusToDosError(v2);
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_e8737fd78cd23c19c4aa7846d1bfb582_Traceguids, v3);
        }
        return;
      }
      v2 = PdcActivationClientRegister(35, &qword_18004CB38);
    }
    else
    {
      v2 = PdcTaskClientRegister(35, &qword_18004CB38);
    }
    if ( v2 >= 0 )
      return;
    goto LABEL_13;
  }
}

```

## disassembly

```asm
0x180030e18  sub     rsp, 28h
0x180030e1c  mov     ecx, cs:dword_18004CB34
0x180030e22  mov     [rsp+28h+arg_0], 0
0x180030e2a  test    ecx, ecx
0x180030e2c  jnz     short loc_180030E5F
0x180030e2e  xor     r8d, r8d
0x180030e31  lea     rdx, [rsp+28h+arg_0]
0x180030e36  xor     ecx, ecx
0x180030e38  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180030e3e  mov     eax, [rsp+28h+arg_0]
0x180030e42  cmp     eax, 5
0x180030e45  jz      short loc_180030E54
0x180030e47  add     eax, 0FFFFFFF5h
0x180030e4a  mov     ecx, 1
0x180030e4f  cmp     eax, 1
0x180030e52  ja      short loc_180030E59
0x180030e54  mov     ecx, 2
0x180030e59  mov     cs:dword_18004CB34, ecx
0x180030e5f  cmp     cs:qword_18004CB38, 0
0x180030e67  jnz     short loc_180030EE4
0x180030e69  sub     ecx, 1
0x180030e6c  jz      short loc_180030E8E
0x180030e6e  cmp     ecx, 1
0x180030e71  jz      short loc_180030E7A
0x180030e73  mov     eax, 0C00000BBh
0x180030e78  jmp     short loc_180030EA4
0x180030e7a  lea     rdx, qword_18004CB38
0x180030e81  mov     ecx, 23h ; '#'
0x180030e86  call    cs:__imp_PdcActivationClientRegister
0x180030e8c  jmp     short loc_180030EA0
0x180030e8e  lea     rdx, qword_18004CB38
0x180030e95  mov     ecx, 23h ; '#'
0x180030e9a  call    cs:__imp_PdcTaskClientRegister
0x180030ea0  test    eax, eax
0x180030ea2  jns     short loc_180030EE4
0x180030ea4  mov     rcx, cs:WPP_GLOBAL_Control
0x180030eab  lea     rdx, WPP_GLOBAL_Control
0x180030eb2  cmp     rcx, rdx
0x180030eb5  jz      short loc_180030EE4
0x180030eb7  test    byte ptr [rcx+1Ch], 1
0x180030ebb  jz      short loc_180030EE4
0x180030ebd  mov     ecx, eax; Status
0x180030ebf  call    cs:__imp_RtlNtStatusToDosError
0x180030ec5  mov     rcx, cs:WPP_GLOBAL_Control
0x180030ecc  lea     r8, WPP_e8737fd78cd23c19c4aa7846d1bfb582_Traceguids
0x180030ed3  mov     edx, 13h
0x180030ed8  mov     r9d, eax
0x180030edb  mov     rcx, [rcx+10h]
0x180030edf  call    WPP_SF_d
0x180030ee4  add     rsp, 28h
0x180030ee8  retn
```
