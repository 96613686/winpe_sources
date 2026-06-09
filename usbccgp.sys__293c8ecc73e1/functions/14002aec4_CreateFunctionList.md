# CreateFunctionList

- ea: `0x14002aec4`
- end: `0x14002b007`
- name: `CreateFunctionList`
- size: `323`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140028f7c`

## callees

- `0x1400088b4`
- `0x14000fb68`
- `0x14002aec4`
- `0x14002b010`
- `0x14002b3bc`

## pseudocode

```c
__int64 __fastcall CreateFunctionList(__int64 a1)
{
  int v2; // edx
  int v3; // edi
  int v4; // r9d
  int v6; // [rsp+40h] [rbp+10h] BYREF
  __int64 v7; // [rsp+48h] [rbp+18h] BYREF

  v7 = 0;
  v6 = 0;
  *(_DWORD *)(a1 + 116) = 0;
  v3 = InvokeDeviceClassCallback(a1, &v7, &v6);
  if ( v3 < 0 )
    goto LABEL_10;
  if ( v6 && v7 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_11;
    v4 = 66;
    goto LABEL_8;
  }
  v3 = ParseUSBInterfaceAssociationDescriptors(a1, &v7, &v6);
  if ( v3 < 0 )
  {
LABEL_10:
    if ( v3 < 0 )
    {
      *(_QWORD *)(a1 + 1136) = 0;
      *(_DWORD *)(a1 + 116) = 0;
      return (unsigned int)v3;
    }
    goto LABEL_11;
  }
  if ( !v6 || !v7 )
  {
    v3 = LegacyGroupInterfaces(a1);
    if ( v3 >= 0 && v6 && v7 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v4 = 68;
      goto LABEL_8;
    }
    goto LABEL_10;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v4 = 67;
LABEL_8:
    LOBYTE(v2) = 4;
    WPP_RECORDER_SF_(*(_QWORD *)(a1 + 1368), v2, 1, v4, (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids);
  }
LABEL_11:
  *(_QWORD *)(a1 + 1136) = v7;
  *(_DWORD *)(a1 + 116) = v6;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14002aec4  mov     [rsp-8+arg_10], rbx
0x14002aec9  mov     [rsp-8+arg_18], rdi
0x14002aece  push    rbp
0x14002aecf  mov     rbp, rsp
0x14002aed2  sub     rsp, 30h
0x14002aed6  lea     r8, [rbp+arg_0]
0x14002aeda  mov     [rbp+arg_8], 0
0x14002aee2  lea     rdx, [rbp+arg_8]
0x14002aee6  mov     [rbp+arg_0], 0
0x14002aeed  mov     rbx, rcx
0x14002aef0  mov     dword ptr [rcx+74h], 0
0x14002aef7  call    InvokeDeviceClassCallback
0x14002aefc  mov     edi, eax
0x14002aefe  test    eax, eax
0x14002af00  js      short loc_14002AF7D
0x14002af02  cmp     [rbp+arg_0], 0
0x14002af06  jnz     loc_14002AFE1
0x14002af0c  lea     r8, [rbp+arg_0]
0x14002af10  mov     rcx, rbx; int
0x14002af13  lea     rdx, [rbp+arg_8]
0x14002af17  call    ParseUSBInterfaceAssociationDescriptors
0x14002af1c  mov     edi, eax
0x14002af1e  test    eax, eax
0x14002af20  js      short loc_14002AF7D
0x14002af22  cmp     [rbp+arg_0], 0
0x14002af26  jz      short loc_14002AF67
0x14002af28  cmp     [rbp+arg_8], 0
0x14002af2d  jz      short loc_14002AF67
0x14002af2f  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002af36  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002af3d  jz      short loc_14002AF81
0x14002af3f  mov     r9d, 43h ; 'C'
0x14002af45  mov     rcx, [rbx+558h]
0x14002af4c  lea     rax, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x14002af53  mov     r8d, 1
0x14002af59  mov     [rsp+30h+var_10], rax
0x14002af5e  mov     dl, 4
0x14002af60  call    WPP_RECORDER_SF_
0x14002af65  jmp     short loc_14002AF81
0x14002af67  lea     r8, [rbp+arg_0]
0x14002af6b  mov     rcx, rbx; int
0x14002af6e  lea     rdx, [rbp+arg_8]
0x14002af72  call    LegacyGroupInterfaces
0x14002af77  mov     edi, eax
0x14002af79  test    eax, eax
0x14002af7b  jns     short loc_14002AFB9
0x14002af7d  test    edi, edi
0x14002af7f  js      short loc_14002AFA5
0x14002af81  mov     rax, [rbp+arg_8]
0x14002af85  mov     [rbx+470h], rax
0x14002af8c  mov     eax, [rbp+arg_0]
0x14002af8f  mov     [rbx+74h], eax
0x14002af92  mov     rbx, [rsp+30h+arg_10]
0x14002af97  mov     eax, edi
0x14002af99  mov     rdi, [rsp+30h+arg_18]
0x14002af9e  add     rsp, 30h
0x14002afa2  pop     rbp
0x14002afa3  retn
0x14002afa5  mov     qword ptr [rbx+470h], 0
0x14002afb0  mov     dword ptr [rbx+74h], 0
0x14002afb7  jmp     short loc_14002AF92
0x14002afb9  cmp     [rbp+arg_0], 0
0x14002afbd  jz      short loc_14002AF7D
0x14002afbf  cmp     [rbp+arg_8], 0
0x14002afc4  jz      short loc_14002AF7D
0x14002afc6  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002afcd  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002afd4  jz      short loc_14002AF7D
0x14002afd6  mov     r9d, 44h ; 'D'
0x14002afdc  jmp     loc_14002AF45
0x14002afe1  cmp     [rbp+arg_8], 0
0x14002afe6  jz      loc_14002AF0C
0x14002afec  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002aff3  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002affa  jz      short loc_14002AF81
0x14002affc  mov     r9d, 42h ; 'B'
0x14002b002  jmp     loc_14002AF45
```
