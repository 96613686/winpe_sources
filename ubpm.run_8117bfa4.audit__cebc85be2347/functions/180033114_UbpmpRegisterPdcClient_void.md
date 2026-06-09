# UbpmpRegisterPdcClient(void)

- ea: `0x180033114`
- end: `0x180033202`
- name: `?UbpmpRegisterPdcClient@@YAXXZ`
- size: `238`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180030390`

## callees

- `0x180033114`
- `0x1800351ec`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180033134`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180033134`
- `ntdll!RtlNtStatusToDosError` at `0x1800331d1`
- `ntdll!RtlNtStatusToDosError` at `0x1800331d1`
- `UMPDC!PdcTaskClientRegister` at `0x1800331a6`
- `UMPDC!PdcTaskClientRegister` at `0x1800331a6`
- `UMPDC!PdcActivationClientRegister` at `0x18003318c`
- `UMPDC!PdcActivationClientRegister` at `0x18003318c`

## pseudocode

```c
void UbpmpRegisterPdcClient(void)
{
  int v0; // ecx
  int v1; // ecx
  NTSTATUS v2; // eax
  ULONG v3; // eax
  int v4; // [rsp+30h] [rbp+8h] BYREF

  v0 = dword_18004FC34;
  v4 = 0;
  if ( !dword_18004FC34 )
  {
    RtlGetDeviceFamilyInfoEnum(0, &v4, 0);
    if ( v4 == 5 || (v0 = 1, (unsigned int)(v4 - 11) <= 1) )
      v0 = 2;
    dword_18004FC34 = v0;
  }
  if ( !qword_18004FC38 )
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
      v2 = PdcActivationClientRegister(35, &qword_18004FC38);
    }
    else
    {
      v2 = PdcTaskClientRegister(35, &qword_18004FC38);
    }
    if ( v2 >= 0 )
      return;
    goto LABEL_13;
  }
}

```

## disassembly

```asm
0x180033114  sub     rsp, 28h
0x180033118  mov     ecx, cs:dword_18004FC34
0x18003311e  mov     [rsp+28h+arg_0], 0
0x180033126  test    ecx, ecx
0x180033128  jnz     short loc_180033161
0x18003312a  xor     r8d, r8d
0x18003312d  lea     rdx, [rsp+28h+arg_0]
0x180033132  xor     ecx, ecx
0x180033134  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18003313b  nop     dword ptr [rax+rax+00h]
0x180033140  mov     eax, [rsp+28h+arg_0]
0x180033144  cmp     eax, 5
0x180033147  jz      short loc_180033156
0x180033149  add     eax, 0FFFFFFF5h
0x18003314c  mov     ecx, 1
0x180033151  cmp     eax, 1
0x180033154  ja      short loc_18003315B
0x180033156  mov     ecx, 2
0x18003315b  mov     cs:dword_18004FC34, ecx
0x180033161  cmp     cs:qword_18004FC38, 0
0x180033169  jnz     loc_1800331FC
0x18003316f  sub     ecx, 1
0x180033172  jz      short loc_18003319A
0x180033174  cmp     ecx, 1
0x180033177  jz      short loc_180033180
0x180033179  mov     eax, 0C00000BBh
0x18003317e  jmp     short loc_1800331B6
0x180033180  lea     rdx, qword_18004FC38
0x180033187  mov     ecx, 23h ; '#'
0x18003318c  call    cs:__imp_PdcActivationClientRegister
0x180033193  nop     dword ptr [rax+rax+00h]
0x180033198  jmp     short loc_1800331B2
0x18003319a  lea     rdx, qword_18004FC38
0x1800331a1  mov     ecx, 23h ; '#'
0x1800331a6  call    cs:__imp_PdcTaskClientRegister
0x1800331ad  nop     dword ptr [rax+rax+00h]
0x1800331b2  test    eax, eax
0x1800331b4  jns     short loc_1800331FC
0x1800331b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800331bd  lea     rdx, WPP_GLOBAL_Control
0x1800331c4  cmp     rcx, rdx
0x1800331c7  jz      short loc_1800331FC
0x1800331c9  test    byte ptr [rcx+1Ch], 1
0x1800331cd  jz      short loc_1800331FC
0x1800331cf  mov     ecx, eax; Status
0x1800331d1  call    cs:__imp_RtlNtStatusToDosError
0x1800331d8  nop     dword ptr [rax+rax+00h]
0x1800331dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800331e4  lea     r8, WPP_e8737fd78cd23c19c4aa7846d1bfb582_Traceguids
0x1800331eb  mov     edx, 13h
0x1800331f0  mov     r9d, eax
0x1800331f3  mov     rcx, [rcx+10h]
0x1800331f7  call    WPP_SF_d
0x1800331fc  add     rsp, 28h
0x180033200  retn
```
