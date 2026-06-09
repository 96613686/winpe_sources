# CheckUSBFnConfiguration

- ea: `0x140043784`
- end: `0x140043a1b`
- name: `CheckUSBFnConfiguration`
- size: `663`
- prototype: `__int64 __fastcall(_DWORD *, const wchar_t *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x140043ebc`
- `0x140044054`

## callees

- `0x1400024b8`
- `0x140043784`
- `0x140044554`
- `0x140044698`
- `0x140044720`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400439cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400439dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400439cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400439dc`
- `ntoskrnl!ExAllocatePool2` at `0x1400437d0`
- `ntoskrnl!ExAllocatePool2` at `0x1400437d0`
- `ntoskrnl!ZwClose` at `0x1400439f5`
- `ntoskrnl!ZwClose` at `0x1400439f5`
- `ntoskrnl!_wcsicmp` at `0x140043947`
- `ntoskrnl!_wcsicmp` at `0x14004396b`
- `ntoskrnl!_wcsicmp` at `0x14004398f`
- `ntoskrnl!_wcsicmp` at `0x140043947`
- `ntoskrnl!_wcsicmp` at `0x14004396b`
- `ntoskrnl!_wcsicmp` at `0x14004398f`
- `ntoskrnl!wcscpy_s` at `0x140043839`
- `ntoskrnl!wcscpy_s` at `0x140043839`
- `ntoskrnl!wcscat_s` at `0x14004384e`
- `ntoskrnl!wcscat_s` at `0x14004384e`

## string_xrefs

- `0x14004382c`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\USBFN\Configurations\`

## pseudocode

```c
__int64 __fastcall CheckUSBFnConfiguration(_DWORD *a1, const wchar_t *a2)
{
  __int64 v4; // rax
  rsize_t v5; // rsi
  wchar_t *Pool2; // rax
  int v7; // edx
  wchar_t *v8; // rbp
  NTSTATUS v9; // edi
  __int64 v10; // rcx
  int v11; // edx
  int v12; // r8d
  int v13; // eax
  int v14; // edx
  wchar_t *v15; // rsi
  __int64 v16; // r15
  __int64 v17; // rax
  HANDLE Handle; // [rsp+80h] [rbp+18h] BYREF
  PVOID P; // [rsp+88h] [rbp+20h] BYREF

  Handle = 0;
  P = 0;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  v5 = 2 * v4 + 146;
  Pool2 = (wchar_t *)ExAllocatePool2(64, v5, 1430540870);
  v8 = Pool2;
  if ( Pool2 )
  {
    wcscpy_s(Pool2, v5, L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\USBFN\\Configurations\\");
    wcscat_s(v8, v5, a2);
    v9 = MyRegOpenKeyForRead(v10, v8, &Handle);
    if ( v9 >= 0 )
    {
      v13 = MyRegQueryString(Handle, L"InterfaceList", &P);
      v15 = (wchar_t *)P;
      v9 = v13;
      if ( v13 >= 0 )
      {
        LODWORD(v16) = 0;
        if ( *(_WORD *)P )
        {
          do
          {
            if ( *a1 == 14 )
              break;
            if ( (*a1 & 2) != 0 || _wcsicmp(&v15[(unsigned int)v16], L"MTP") )
            {
              if ( (*(_BYTE *)a1 & 4) != 0 || _wcsicmp(&v15[(unsigned int)v16], L"IpOverUsb") )
              {
                if ( (*(_BYTE *)a1 & 8) == 0 && !_wcsicmp(&v15[(unsigned int)v16], L"VidStream") )
                  *a1 |= 8u;
              }
              else
              {
                *a1 |= 4u;
              }
            }
            else
            {
              *a1 |= 2u;
            }
            v17 = -1;
            do
              ++v17;
            while ( v15[(unsigned int)v16 + v17] );
            v16 = (unsigned int)(v17 + v16 + 1);
          }
          while ( v15[v16] );
        }
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v14) = 3;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v14,
          1,
          28,
          (__int64)WPP_5169c4c8089132207a438b4341aed5b6_Traceguids,
          v13);
      }
      if ( v15 )
        ExFreePoolWithTag(v15, 0);
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 4;
      WPP_RECORDER_SF_Sd(WPP_GLOBAL_Control->DeviceExtension, v11, v12, 27);
    }
    ExFreePoolWithTag(v8, 0);
  }
  else
  {
    v9 = -1073741670;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 3;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        1,
        26,
        (__int64)WPP_5169c4c8089132207a438b4341aed5b6_Traceguids,
        -1073741670);
    }
  }
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140043784  mov     rax, rsp
0x140043787  mov     [rax+8], rbx
0x14004378b  mov     [rax+10h], rbp
0x14004378f  push    rsi
0x140043790  push    rdi
0x140043791  push    r12
0x140043793  push    r14
0x140043795  push    r15
0x140043797  sub     rsp, 40h
0x14004379b  xor     r12d, r12d
0x14004379e  mov     rdi, rdx
0x1400437a1  mov     [rax+18h], r12
0x1400437a5  mov     rbx, rcx
0x1400437a8  mov     [rax+20h], r12
0x1400437ac  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400437b0  inc     rax
0x1400437b3  cmp     [rdx+rax*2], r12w
0x1400437b8  jnz     short loc_1400437B0
0x1400437ba  lea     rsi, ds:92h[rax*2]
0x1400437c2  mov     r8d, 55445246h
0x1400437c8  mov     rdx, rsi
0x1400437cb  mov     ecx, 40h ; '@'
0x1400437d0  call    cs:__imp_ExAllocatePool2
0x1400437d7  nop     dword ptr [rax+rax+00h]
0x1400437dc  mov     rbp, rax
0x1400437df  test    rax, rax
0x1400437e2  jnz     short loc_14004382C
0x1400437e4  mov     edi, 0C000009Ah
0x1400437e9  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400437f0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400437f7  jz      loc_1400439E8
0x1400437fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140043804  lea     rax, WPP_5169c4c8089132207a438b4341aed5b6_Traceguids
0x14004380b  lea     r9d, [rbp+1Ah]
0x14004380f  mov     dword ptr [rsp+68h+var_40], edi
0x140043813  lea     r8d, [rbp+1]
0x140043817  mov     [rsp+68h+var_48], rax
0x14004381c  mov     dl, 3
0x14004381e  mov     rcx, [rcx+40h]
0x140043822  call    WPP_RECORDER_SF_d
0x140043827  jmp     loc_1400439E8
0x14004382c  lea     r8, aRegistryMachin_2; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x140043833  mov     rdx, rsi; SizeInWords
0x140043836  mov     rcx, rbp; Dst
0x140043839  call    cs:__imp_wcscpy_s
0x140043840  nop     dword ptr [rax+rax+00h]
0x140043845  mov     r8, rdi; Src
0x140043848  mov     rdx, rsi; SizeInWords
0x14004384b  mov     rcx, rbp; Dst
0x14004384e  call    cs:__imp_wcscat_s
0x140043855  nop     dword ptr [rax+rax+00h]
0x14004385a  lea     r8, [rsp+68h+Handle]
0x140043862  mov     rdx, rbp
0x140043865  call    MyRegOpenKeyForRead
0x14004386a  mov     edi, eax
0x14004386c  test    eax, eax
0x14004386e  jns     short loc_1400438AA
0x140043870  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140043877  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004387e  jz      loc_1400439D7
0x140043884  mov     rcx, cs:WPP_GLOBAL_Control
0x14004388b  mov     r9d, 1Bh
0x140043891  mov     [rsp+68h+var_38], edi
0x140043895  mov     dl, 4
0x140043897  mov     [rsp+68h+var_40], rbp
0x14004389c  mov     rcx, [rcx+40h]
0x1400438a0  call    WPP_RECORDER_SF_Sd
0x1400438a5  jmp     loc_1400439D7
0x1400438aa  mov     rcx, [rsp+68h+Handle]; KeyHandle
0x1400438b2  lea     r8, [rsp+68h+P]
0x1400438ba  lea     rdx, aInterfacelist; "InterfaceList"
0x1400438c1  call    MyRegQueryString
0x1400438c6  mov     rsi, [rsp+68h+P]
0x1400438ce  mov     edi, eax
0x1400438d0  test    eax, eax
0x1400438d2  jns     short loc_140043919
0x1400438d4  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400438db  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400438e2  jz      loc_1400439C1
0x1400438e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400438ef  lea     rax, WPP_5169c4c8089132207a438b4341aed5b6_Traceguids
0x1400438f6  mov     r9d, 1Ch
0x1400438fc  mov     dword ptr [rsp+68h+var_40], edi
0x140043900  mov     dl, 3
0x140043902  mov     [rsp+68h+var_48], rax
0x140043907  mov     rcx, [rcx+40h]
0x14004390b  lea     r8d, [r9-1Bh]
0x14004390f  call    WPP_RECORDER_SF_d
0x140043914  jmp     loc_1400439C1
0x140043919  mov     r15d, r12d
0x14004391c  cmp     [rsi], r12w
0x140043920  jz      loc_1400439C1
0x140043926  mov     ecx, [rbx]
0x140043928  cmp     ecx, 0Eh
0x14004392b  jz      loc_1400439C1
0x140043931  mov     eax, r15d
0x140043934  lea     r14, [rsi+rax*2]
0x140043938  test    cl, 2
0x14004393b  jnz     short loc_14004395C
0x14004393d  lea     rdx, aMtp; "MTP"
0x140043944  mov     rcx, r14; Str1
0x140043947  call    cs:__imp__wcsicmp
0x14004394e  nop     dword ptr [rax+rax+00h]
0x140043953  test    eax, eax
0x140043955  jnz     short loc_14004395C
0x140043957  or      dword ptr [rbx], 2
0x14004395a  jmp     short loc_1400439A2
0x14004395c  test    byte ptr [rbx], 4
0x14004395f  jnz     short loc_140043980
0x140043961  lea     rdx, aIpoverusb; "IpOverUsb"
0x140043968  mov     rcx, r14; Str1
0x14004396b  call    cs:__imp__wcsicmp
0x140043972  nop     dword ptr [rax+rax+00h]
0x140043977  test    eax, eax
0x140043979  jnz     short loc_140043980
0x14004397b  or      dword ptr [rbx], 4
0x14004397e  jmp     short loc_1400439A2
0x140043980  test    byte ptr [rbx], 8
0x140043983  jnz     short loc_1400439A2
0x140043985  lea     rdx, aVidstream; "VidStream"
0x14004398c  mov     rcx, r14; Str1
0x14004398f  call    cs:__imp__wcsicmp
0x140043996  nop     dword ptr [rax+rax+00h]
0x14004399b  test    eax, eax
0x14004399d  jnz     short loc_1400439A2
0x14004399f  or      dword ptr [rbx], 8
0x1400439a2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400439a6  inc     rax
0x1400439a9  cmp     [r14+rax*2], r12w
0x1400439ae  jnz     short loc_1400439A6
0x1400439b0  inc     r15d
0x1400439b3  add     r15d, eax
0x1400439b6  cmp     [rsi+r15*2], r12w
0x1400439bb  jnz     loc_140043926
0x1400439c1  test    rsi, rsi
0x1400439c4  jz      short loc_1400439D7
0x1400439c6  xor     edx, edx; Tag
0x1400439c8  mov     rcx, rsi; P
0x1400439cb  call    cs:__imp_ExFreePoolWithTag
0x1400439d2  nop     dword ptr [rax+rax+00h]
0x1400439d7  xor     edx, edx; Tag
0x1400439d9  mov     rcx, rbp; P
0x1400439dc  call    cs:__imp_ExFreePoolWithTag
0x1400439e3  nop     dword ptr [rax+rax+00h]
0x1400439e8  mov     rcx, [rsp+68h+Handle]; Handle
0x1400439f0  test    rcx, rcx
0x1400439f3  jz      short loc_140043A01
0x1400439f5  call    cs:__imp_ZwClose
0x1400439fc  nop     dword ptr [rax+rax+00h]
0x140043a01  mov     rbx, [rsp+68h+arg_0]
0x140043a06  mov     eax, edi
0x140043a08  mov     rbp, [rsp+68h+arg_8]
0x140043a0d  add     rsp, 40h
0x140043a11  pop     r15
0x140043a13  pop     r14
0x140043a15  pop     r12
0x140043a17  pop     rdi
0x140043a18  pop     rsi
0x140043a19  retn
```
