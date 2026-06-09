# CUwfStaticVolumeConfiguration::SetTightBindingConfiguration(ushort const *)

- ea: `0x180009f38`
- end: `0x18000a0b1`
- name: `?SetTightBindingConfiguration@CUwfStaticVolumeConfiguration@@AEAAJPEBG@Z`
- size: `377`
- prototype: `__int64 __fastcall(CUwfConfiguration **this, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000bc90`

## callees

- `0x1800054d0`
- `0x180009f38`
- `0x18000bf50`
- `0x18000c540`
- `0x18000c5e0`
- `0x18000c630`
- `0x18001155c`
- `0x18001b020`

## pseudocode

```c
__int64 __fastcall CUwfStaticVolumeConfiguration::SetTightBindingConfiguration(
        CUwfConfiguration **this,
        LPCWSTR lpFileName)
{
  int TightBindingInfo; // ecx
  _PARTITION_STYLE v4; // ebx
  int v5; // eax
  struct _GUID *v7; // [rsp+20h] [rbp-89h]
  struct _GUID v8; // [rsp+70h] [rbp-39h] BYREF
  _PARTITION_STYLE v9; // [rsp+80h] [rbp-29h] BYREF
  unsigned int v10; // [rsp+84h] [rbp-25h] BYREF
  union _LARGE_INTEGER v11; // [rsp+88h] [rbp-21h] BYREF
  unsigned __int16 v12[40]; // [rsp+90h] [rbp-19h] BYREF

  v9 = PARTITION_STYLE_MBR;
  v11.QuadPart = 0;
  v10 = 0;
  v8 = 0;
  TightBindingInfo = VolumeGetTightBindingInfo(lpFileName, &v9, &v11, &v10, &v8);
  if ( TightBindingInfo >= 0 )
  {
    v4 = v9;
    TightBindingInfo = CUwfStaticVolumeConfiguration::set_PartitionStyle(this, v9);
    if ( TightBindingInfo >= 0 )
    {
      if ( v4 )
      {
        if ( v4 == PARTITION_STYLE_GPT )
        {
          LODWORD(v7) = v8.Data2;
          TightBindingInfo = StringCchPrintfW(
                               v12,
                               0x27u,
                               L"{%08.8X-%04.4X-%04.4X-%02.2X%02.2X-%02.2X%02.2X%02.2X%02.2X%02.2X%02.2X}",
                               v8.Data1,
                               v7,
                               v8.Data3,
                               v8.Data4[0],
                               v8.Data4[1],
                               v8.Data4[2],
                               v8.Data4[3],
                               v8.Data4[4],
                               v8.Data4[5],
                               v8.Data4[6],
                               v8.Data4[7]);
          if ( TightBindingInfo >= 0 )
          {
            v5 = CUwfStaticVolumeConfiguration::set_PartitionGUID(this, v12);
LABEL_9:
            TightBindingInfo = v5;
            if ( v5 >= 0 )
              return (unsigned int)TightBindingInfo;
          }
        }
        else
        {
          TightBindingInfo = -2147024846;
        }
      }
      else
      {
        TightBindingInfo = CUwfStaticVolumeConfiguration::set_PartitionOffset(this, v11.QuadPart);
        if ( TightBindingInfo >= 0 )
        {
          v5 = CUwfStaticVolumeConfiguration::set_DiskSignature(this, v10);
          goto LABEL_9;
        }
      }
    }
  }
  *((_DWORD *)this[3] + 4) = TightBindingInfo;
  return (unsigned int)TightBindingInfo;
}

```

## disassembly

```asm
0x180009f38  mov     [rsp-8+arg_10], rbx
0x180009f3d  mov     [rsp-8+arg_18], rsi
0x180009f42  push    rbp
0x180009f43  push    rdi
0x180009f44  push    r14
0x180009f46  lea     rbp, [rsp-47h]
0x180009f4b  sub     rsp, 0F0h
0x180009f52  mov     rax, cs:__security_cookie
0x180009f59  xor     rax, rsp
0x180009f5c  mov     [rbp+57h+var_20], rax
0x180009f60  mov     r14, rcx
0x180009f63  mov     [rbp+57h+var_80], 0
0x180009f6a  mov     rax, rdx
0x180009f6d  mov     qword ptr [rbp+57h+var_78], 0
0x180009f75  lea     rcx, [rbp+57h+var_90]
0x180009f79  mov     [rbp+57h+var_7C], 0
0x180009f80  mov     [rsp+100h+var_E0], rcx; struct _GUID *
0x180009f85  lea     r9, [rbp+57h+var_7C]; unsigned int *
0x180009f89  xorps   xmm0, xmm0
0x180009f8c  lea     r8, [rbp+57h+var_78]; union _LARGE_INTEGER *
0x180009f90  mov     rcx, rax; lpFileName
0x180009f93  lea     rdx, [rbp+57h+var_80]; enum _PARTITION_STYLE *
0x180009f97  movups  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x180009f9b  call    ?VolumeGetTightBindingInfo@@YAJPEBGPEAW4_PARTITION_STYLE@@PEAT_LARGE_INTEGER@@PEAKPEAU_GUID@@@Z; VolumeGetTightBindingInfo(ushort const *,_PARTITION_STYLE *,_LARGE_INTEGER *,ulong *,_GUID *)
0x180009fa0  mov     ecx, eax
0x180009fa2  test    eax, eax
0x180009fa4  js      loc_18000A084
0x180009faa  mov     ebx, [rbp+57h+var_80]
0x180009fad  mov     rcx, r14; this
0x180009fb0  mov     edx, ebx; enum _PARTITION_STYLE
0x180009fb2  call    ?set_PartitionStyle@CUwfStaticVolumeConfiguration@@QEAAJW4_PARTITION_STYLE@@@Z; CUwfStaticVolumeConfiguration::set_PartitionStyle(_PARTITION_STYLE)
0x180009fb7  mov     ecx, eax
0x180009fb9  test    eax, eax
0x180009fbb  js      loc_18000A084
0x180009fc1  test    ebx, ebx
0x180009fc3  jnz     short loc_180009FEB
0x180009fc5  mov     rdx, qword ptr [rbp+57h+var_78]; unsigned __int64
0x180009fc9  mov     rcx, r14; this
0x180009fcc  call    ?set_PartitionOffset@CUwfStaticVolumeConfiguration@@QEAAJ_K@Z; CUwfStaticVolumeConfiguration::set_PartitionOffset(unsigned __int64)
0x180009fd1  mov     ecx, eax
0x180009fd3  test    eax, eax
0x180009fd5  js      loc_18000A084
0x180009fdb  mov     edx, [rbp+57h+var_7C]; unsigned int
0x180009fde  mov     rcx, r14; this
0x180009fe1  call    ?set_DiskSignature@CUwfStaticVolumeConfiguration@@QEAAJK@Z; CUwfStaticVolumeConfiguration::set_DiskSignature(ulong)
0x180009fe6  jmp     loc_18000A077
0x180009feb  cmp     ebx, 1
0x180009fee  jnz     loc_18000A07F
0x180009ff4  movzx   r9d, [rbp+57h+var_90.Data4+3]
0x180009ff9  movzx   eax, [rbp+57h+var_90.Data4+7]
0x180009ffd  movzx   ecx, [rbp+57h+var_90.Data4+6]
0x18000a001  movzx   edx, [rbp+57h+var_90.Data4+5]
0x18000a005  movzx   r8d, [rbp+57h+var_90.Data4+4]
0x18000a00a  movzx   r10d, [rbp+57h+var_90.Data4+2]
0x18000a00f  movzx   r11d, [rbp+57h+var_90.Data4+1]
0x18000a014  movzx   ebx, [rbp+57h+var_90.Data4]
0x18000a018  movzx   edi, [rbp+57h+var_90.Data3]
0x18000a01c  movzx   esi, [rbp+57h+var_90.Data2]
0x18000a020  mov     [rsp+100h+var_98], eax
0x18000a024  mov     [rsp+100h+var_A0], ecx
0x18000a028  lea     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x18000a02c  mov     [rsp+100h+var_A8], edx
0x18000a030  mov     edx, 27h ; '''; unsigned __int64
0x18000a035  mov     [rsp+100h+var_B0], r8d
0x18000a03a  lea     r8, a088x044x044x02; "{%08.8X-%04.4X-%04.4X-%02.2X%02.2X-%02."...
0x18000a041  mov     [rsp+100h+var_B8], r9d
0x18000a046  mov     r9d, [rbp+57h+var_90.Data1]
0x18000a04a  mov     [rsp+100h+var_C0], r10d
0x18000a04f  mov     [rsp+100h+var_C8], r11d
0x18000a054  mov     [rsp+100h+var_D0], ebx
0x18000a058  mov     [rsp+100h+var_D8], edi
0x18000a05c  mov     dword ptr [rsp+100h+var_E0], esi
0x18000a060  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a065  mov     ecx, eax
0x18000a067  test    eax, eax
0x18000a069  js      short loc_18000A084
0x18000a06b  lea     rdx, [rbp+57h+var_70]; unsigned __int16 *
0x18000a06f  mov     rcx, r14; this
0x18000a072  call    ?set_PartitionGUID@CUwfStaticVolumeConfiguration@@QEAAJPEBG@Z; CUwfStaticVolumeConfiguration::set_PartitionGUID(ushort const *)
0x18000a077  mov     ecx, eax
0x18000a079  test    eax, eax
0x18000a07b  js      short loc_18000A084
0x18000a07d  jmp     short loc_18000A08B
0x18000a07f  mov     ecx, 80070032h
0x18000a084  mov     rax, [r14+18h]
0x18000a088  mov     [rax+10h], ecx
0x18000a08b  mov     eax, ecx
0x18000a08d  mov     rcx, [rbp+57h+var_20]
0x18000a091  xor     rcx, rsp; StackCookie
0x18000a094  call    __security_check_cookie
0x18000a099  lea     r11, [rsp+100h+var_10]
0x18000a0a1  mov     rbx, [r11+30h]
0x18000a0a5  mov     rsi, [r11+38h]
0x18000a0a9  mov     rsp, r11
0x18000a0ac  pop     r14
0x18000a0ae  pop     rdi
0x18000a0af  pop     rbp
0x18000a0b0  retn
```
