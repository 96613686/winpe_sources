# VmpInitializeInterfaces(VM_VOLUME_EXTENSION *)

- ea: `0x140004028`
- end: `0x140004429`
- name: `?VmpInitializeInterfaces@@YAJPEAVVM_VOLUME_EXTENSION@@@Z`
- size: `1025`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x1400046a4`

## callees

- `0x140002db0`
- `0x140004028`
- `0x140005050`
- `0x140005540`

## import_xrefs

- `ntoskrnl!IoRegisterDeviceInterface` at `0x1400040aa`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x1400040cf`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x1400040fa`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x1400040aa`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x1400040cf`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x1400040fa`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400043ac`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400043d7`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400043f4`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400043ac`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400043d7`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400043f4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004276`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004276`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x1400041d3`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x140004213`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x140004259`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x1400042c1`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x140004309`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x140004341`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x140004379`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x1400041d3`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x140004213`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x140004259`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x1400042c1`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x140004309`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x140004341`
- `ntoskrnl!IoSetDeviceInterfacePropertyData` at `0x140004379`

## pseudocode

```c
int __fastcall VmpInitializeInterfaces(struct VM_VOLUME_EXTENSION *a1)
{
  __int64 v2; // rax
  int v3; // r14d
  int v4; // r15d
  int result; // eax
  unsigned int i; // edi
  char *v7; // rcx
  char v8; // [rsp+40h] [rbp-89h] BYREF
  char v9; // [rsp+41h] [rbp-88h] BYREF
  _BYTE v10[6]; // [rsp+42h] [rbp-87h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-81h] BYREF
  WCHAR v12[72]; // [rsp+60h] [rbp-69h] BYREF

  memset(v12, 0, sizeof(v12));
  v2 = *(_QWORD *)a1;
  v10[0] = 0;
  v8 = 0;
  v9 = 0;
  DestinationString = 0;
  v3 = *(_DWORD *)(v2 + 48);
  v4 = *(_DWORD *)(*(_QWORD *)a1 + 52LL);
  result = IoRegisterDeviceInterface(
             *(PDEVICE_OBJECT *)a1,
             &GUID_DEVINTERFACE_VOLUME,
             0,
             (PUNICODE_STRING)((char *)a1 + 168));
  if ( result >= 0 )
  {
    result = IoRegisterDeviceInterface(
               *(PDEVICE_OBJECT *)a1,
               &GUID_DEVINTERFACE_HIDDEN_VOLUME,
               0,
               (PUNICODE_STRING)((char *)a1 + 184));
    if ( result >= 0 )
    {
      result = IoRegisterDeviceInterface(
                 *(PDEVICE_OBJECT *)a1,
                 &GUID_DEVINTERFACE_SERVICE_VOLUME,
                 0,
                 (PUNICODE_STRING)((char *)a1 + 200));
      if ( result >= 0 )
      {
        if ( *((_BYTE *)a1 + 426)
          || (result = VmpSendDeviceControl(*((PDEVICE_OBJECT *)a1 + 43), 0x70048u, 0, 0, v12, 0x90u), result >= 0) )
        {
          v10[0] = -((v3 & 0x600100) != 0);
          v8 = -((v4 & 0x40000) != 0);
          v9 = ((v4 & 1) == 0) - 1;
          for ( i = 0; i < 3; ++i )
          {
            if ( !*((_BYTE *)a1 + 426) )
            {
              result = IoSetDeviceInterfacePropertyData(
                         (char *)a1 + 16 * i + 168,
                         &DEVPKEY_Storage_Disk_Number,
                         0,
                         0,
                         7,
                         4,
                         (char *)a1 + 384);
              if ( result < 0 )
                return result;
              result = IoSetDeviceInterfacePropertyData(
                         (char *)a1 + 16 * i + 168,
                         &DEVPKEY_Storage_Partition_Number,
                         0,
                         0,
                         7,
                         4,
                         (char *)a1 + 388);
              if ( result < 0 )
                return result;
              v7 = (char *)a1 + 16 * i + 168;
              if ( *((_BYTE *)a1 + 424) )
              {
                result = IoSetDeviceInterfacePropertyData(v7, &DEVPKEY_Storage_Gpt_Type, 0, 0, 13, 16, &v12[16]);
                if ( result < 0 )
                  return result;
                RtlInitUnicodeString(&DestinationString, &v12[36]);
                result = IoSetDeviceInterfacePropertyData(
                           (char *)a1 + 16 * i + 168,
                           &DEVPKEY_Storage_Gpt_Name,
                           0,
                           0,
                           18,
                           DestinationString.MaximumLength,
                           DestinationString.Buffer);
              }
              else
              {
                result = IoSetDeviceInterfacePropertyData(v7, &DEVPKEY_Storage_Mbr_Type, 0, 0, 3, 1, &v12[16]);
              }
              if ( result < 0 )
                return result;
            }
            result = IoSetDeviceInterfacePropertyData(
                       (char *)a1 + 16 * i + 168,
                       &DEVPKEY_Storage_Portable,
                       0,
                       0,
                       17,
                       1,
                       &v8);
            if ( result < 0 )
              return result;
            result = IoSetDeviceInterfacePropertyData(
                       (char *)a1 + 16 * i + 168,
                       &DEVPKEY_Storage_Removable_Media,
                       0,
                       0,
                       17,
                       1,
                       &v9);
            if ( result < 0 )
              return result;
            result = IoSetDeviceInterfacePropertyData(
                       (char *)a1 + 16 * i + 168,
                       &DEVPKEY_Storage_System_Critical,
                       0,
                       0,
                       17,
                       1,
                       v10);
            if ( result < 0 )
              return result;
          }
          result = IoSetDeviceInterfaceState(
                     (PUNICODE_STRING)((char *)a1 + (-(__int64)(*((_BYTE *)a1 + 152) != 0) & 0xFFFFFFFFFFFFFFF0uLL)
                                                  + 184),
                     0);
          if ( result >= 0 )
          {
            result = IoSetDeviceInterfaceState(
                       (PUNICODE_STRING)((char *)a1 + (*((_BYTE *)a1 + 152) != 0 ? 184LL : 168LL)),
                       1u);
            if ( result >= 0 )
              return IoSetDeviceInterfaceState((PUNICODE_STRING)((char *)a1 + 200), *((_BYTE *)a1 + 153) != 0);
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140004028  mov     [rsp-8+arg_8], rbx
0x14000402d  mov     [rsp-8+arg_10], rsi
0x140004032  push    rbp
0x140004033  push    rdi
0x140004034  push    r12
0x140004036  push    r14
0x140004038  push    r15
0x14000403a  lea     rbp, [rsp-37h]
0x14000403f  sub     rsp, 100h
0x140004046  mov     rax, cs:__security_cookie
0x14000404d  xor     rax, rsp
0x140004050  mov     [rbp+57h+var_30], rax
0x140004054  mov     rbx, rcx
0x140004057  xor     edx, edx; Val
0x140004059  lea     rcx, [rbp+57h+var_C0]; void *
0x14000405d  mov     r8d, 90h; Size
0x140004063  call    memset
0x140004068  mov     rax, [rbx]
0x14000406b  lea     rsi, [rbx+0A8h]
0x140004072  mov     [rsp+120h+var_DE], 0
0x140004077  lea     rdx, GUID_DEVINTERFACE_VOLUME; InterfaceClassGuid
0x14000407e  mov     [rsp+120h+var_E0], 0
0x140004083  xorps   xmm0, xmm0
0x140004086  mov     [rsp+120h+var_DF], 0
0x14000408b  mov     r9, rsi; SymbolicLinkName
0x14000408e  movups  xmmword ptr [rsp+120h+DestinationString.Length], xmm0
0x140004093  mov     r14d, [rax+30h]
0x140004097  xor     r8d, r8d; ReferenceString
0x14000409a  mov     rax, [rbx]
0x14000409d  mov     r15d, [rax+34h]
0x1400040a1  mov     rax, [rbx]
0x1400040a4  mov     edi, [rax+34h]
0x1400040a7  mov     rcx, [rbx]; PhysicalDeviceObject
0x1400040aa  call    cs:__imp_IoRegisterDeviceInterface
0x1400040b1  nop     dword ptr [rax+rax+00h]
0x1400040b6  test    eax, eax
0x1400040b8  js      loc_140004400
0x1400040be  mov     rcx, [rbx]; PhysicalDeviceObject
0x1400040c1  lea     r9, [rsi+10h]; SymbolicLinkName
0x1400040c5  xor     r8d, r8d; ReferenceString
0x1400040c8  lea     rdx, GUID_DEVINTERFACE_HIDDEN_VOLUME; InterfaceClassGuid
0x1400040cf  call    cs:__imp_IoRegisterDeviceInterface
0x1400040d6  nop     dword ptr [rax+rax+00h]
0x1400040db  test    eax, eax
0x1400040dd  js      loc_140004400
0x1400040e3  mov     rcx, [rbx]; PhysicalDeviceObject
0x1400040e6  lea     r12, [rbx+0C8h]
0x1400040ed  mov     r9, r12; SymbolicLinkName
0x1400040f0  lea     rdx, GUID_DEVINTERFACE_SERVICE_VOLUME; InterfaceClassGuid
0x1400040f7  xor     r8d, r8d; ReferenceString
0x1400040fa  call    cs:__imp_IoRegisterDeviceInterface
0x140004101  nop     dword ptr [rax+rax+00h]
0x140004106  test    eax, eax
0x140004108  js      loc_140004400
0x14000410e  cmp     byte ptr [rbx+1AAh], 0
0x140004115  jnz     short loc_140004147
0x140004117  mov     rcx, [rbx+158h]; DeviceObject
0x14000411e  lea     rax, [rbp+57h+var_C0]
0x140004122  mov     [rsp+120h+var_F8], 90h; ULONG
0x14000412a  xor     r9d, r9d; InputBufferLength
0x14000412d  xor     r8d, r8d; InputBuffer
0x140004130  mov     [rsp+120h+var_100], rax; PVOID
0x140004135  mov     edx, 70048h; IoControlCode
0x14000413a  call    VmpSendDeviceControl
0x14000413f  test    eax, eax
0x140004141  js      loc_140004400
0x140004147  and     r14d, 600100h
0x14000414e  not     dil
0x140004151  neg     r14d
0x140004154  mov     r14d, 1
0x14000415a  sbb     al, al
0x14000415c  and     r15d, 40000h
0x140004163  neg     r15d
0x140004166  mov     [rsp+120h+var_DE], al
0x14000416a  sbb     al, al
0x14000416c  lea     r15d, [r14+10h]
0x140004170  and     dil, r14b
0x140004173  mov     [rsp+120h+var_E0], al
0x140004177  sub     dil, r14b
0x14000417a  mov     [rsp+120h+var_DF], dil
0x14000417f  xor     edi, edi
0x140004181  cmp     edi, 3
0x140004184  jnb     loc_140004391
0x14000418a  cmp     byte ptr [rbx+1AAh], 0
0x140004191  jnz     loc_1400042D5
0x140004197  lea     rax, [rbx+180h]
0x14000419e  mov     esi, edi
0x1400041a0  mov     [rsp+120h+var_F0], rax
0x1400041a5  lea     rdx, DEVPKEY_Storage_Disk_Number
0x1400041ac  shl     rsi, 4
0x1400041b0  xor     r9d, r9d
0x1400041b3  add     rsi, 0A8h
0x1400041ba  mov     [rsp+120h+var_F8], 4
0x1400041c2  add     rsi, rbx
0x1400041c5  mov     dword ptr [rsp+120h+var_100], 7
0x1400041cd  mov     rcx, rsi
0x1400041d0  xor     r8d, r8d
0x1400041d3  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x1400041da  nop     dword ptr [rax+rax+00h]
0x1400041df  test    eax, eax
0x1400041e1  js      loc_140004400
0x1400041e7  lea     rax, [rbx+184h]
0x1400041ee  xor     r9d, r9d
0x1400041f1  mov     [rsp+120h+var_F0], rax
0x1400041f6  lea     rdx, DEVPKEY_Storage_Partition_Number
0x1400041fd  mov     [rsp+120h+var_F8], 4
0x140004205  xor     r8d, r8d
0x140004208  mov     rcx, rsi
0x14000420b  mov     dword ptr [rsp+120h+var_100], 7
0x140004213  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x14000421a  nop     dword ptr [rax+rax+00h]
0x14000421f  test    eax, eax
0x140004221  js      loc_140004400
0x140004227  xor     r9d, r9d
0x14000422a  lea     rax, [rbp+57h+var_A0]
0x14000422e  xor     r8d, r8d
0x140004231  mov     [rsp+120h+var_F0], rax
0x140004236  mov     rcx, rsi
0x140004239  cmp     [rbx+1A8h], r8b
0x140004240  jz      short loc_1400042AD
0x140004242  mov     [rsp+120h+var_F8], 10h
0x14000424a  lea     rdx, DEVPKEY_Storage_Gpt_Type
0x140004251  mov     dword ptr [rsp+120h+var_100], 0Dh
0x140004259  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x140004260  nop     dword ptr [rax+rax+00h]
0x140004265  test    eax, eax
0x140004267  js      loc_140004400
0x14000426d  lea     rdx, [rbp+57h+SourceString]; SourceString
0x140004271  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x140004276  call    cs:__imp_RtlInitUnicodeString
0x14000427d  nop     dword ptr [rax+rax+00h]
0x140004282  movzx   edx, [rbp+57h+DestinationString.MaximumLength]
0x140004286  xor     r9d, r9d
0x140004289  mov     rax, [rbp+57h+DestinationString.Buffer]
0x14000428d  xor     r8d, r8d
0x140004290  mov     [rsp+120h+var_F0], rax
0x140004295  mov     rcx, rsi
0x140004298  mov     [rsp+120h+var_F8], edx
0x14000429c  lea     rdx, DEVPKEY_Storage_Gpt_Name
0x1400042a3  mov     dword ptr [rsp+120h+var_100], 12h
0x1400042ab  jmp     short loc_1400042C1
0x1400042ad  mov     [rsp+120h+var_F8], r14d
0x1400042b2  lea     rdx, DEVPKEY_Storage_Mbr_Type
0x1400042b9  mov     dword ptr [rsp+120h+var_100], 3
0x1400042c1  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x1400042c8  nop     dword ptr [rax+rax+00h]
0x1400042cd  test    eax, eax
0x1400042cf  js      loc_140004400
0x1400042d5  lea     rax, [rsp+120h+var_E0]
0x1400042da  mov     esi, edi
0x1400042dc  mov     [rsp+120h+var_F0], rax
0x1400042e1  lea     rdx, DEVPKEY_Storage_Portable
0x1400042e8  shl     rsi, 4
0x1400042ec  xor     r9d, r9d
0x1400042ef  add     rsi, 0A8h
0x1400042f6  mov     [rsp+120h+var_F8], r14d
0x1400042fb  add     rsi, rbx
0x1400042fe  mov     dword ptr [rsp+120h+var_100], r15d
0x140004303  mov     rcx, rsi
0x140004306  xor     r8d, r8d
0x140004309  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x140004310  nop     dword ptr [rax+rax+00h]
0x140004315  test    eax, eax
0x140004317  js      loc_140004400
0x14000431d  lea     rax, [rsp+120h+var_DF]
0x140004322  xor     r9d, r9d
0x140004325  mov     [rsp+120h+var_F0], rax
0x14000432a  lea     rdx, DEVPKEY_Storage_Removable_Media
0x140004331  mov     [rsp+120h+var_F8], r14d
0x140004336  xor     r8d, r8d
0x140004339  mov     rcx, rsi
0x14000433c  mov     dword ptr [rsp+120h+var_100], r15d
0x140004341  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x140004348  nop     dword ptr [rax+rax+00h]
0x14000434d  test    eax, eax
0x14000434f  js      loc_140004400
0x140004355  lea     rax, [rsp+120h+var_DE]
0x14000435a  xor     r9d, r9d
0x14000435d  mov     [rsp+120h+var_F0], rax
0x140004362  lea     rdx, DEVPKEY_Storage_System_Critical
0x140004369  mov     [rsp+120h+var_F8], r14d
0x14000436e  xor     r8d, r8d
0x140004371  mov     rcx, rsi
0x140004374  mov     dword ptr [rsp+120h+var_100], r15d
0x140004379  call    cs:__imp_IoSetDeviceInterfacePropertyData
0x140004380  nop     dword ptr [rax+rax+00h]
0x140004385  test    eax, eax
0x140004387  js      short loc_140004400
0x140004389  add     edi, r14d
0x14000438c  jmp     loc_140004181
0x140004391  mov     al, [rbx+98h]
0x140004397  neg     al
0x140004399  sbb     rcx, rcx
0x14000439c  xor     edx, edx; Enable
0x14000439e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1400043a2  add     rcx, 0B8h
0x1400043a9  add     rcx, rbx; SymbolicLinkName
0x1400043ac  call    cs:__imp_IoSetDeviceInterfaceState
0x1400043b3  nop     dword ptr [rax+rax+00h]
0x1400043b8  test    eax, eax
0x1400043ba  js      short loc_140004400
0x1400043bc  mov     al, [rbx+98h]
0x1400043c2  mov     dl, r14b; Enable
0x1400043c5  neg     al
0x1400043c7  sbb     rcx, rcx
0x1400043ca  and     ecx, 10h
0x1400043cd  add     rcx, 0A8h
0x1400043d4  add     rcx, rbx; SymbolicLinkName
0x1400043d7  call    cs:__imp_IoSetDeviceInterfaceState
0x1400043de  nop     dword ptr [rax+rax+00h]
0x1400043e3  test    eax, eax
0x1400043e5  js      short loc_140004400
0x1400043e7  cmp     byte ptr [rbx+99h], 0
0x1400043ee  mov     rcx, r12; SymbolicLinkName
0x1400043f1  setnz   dl; Enable
0x1400043f4  call    cs:__imp_IoSetDeviceInterfaceState
0x1400043fb  nop     dword ptr [rax+rax+00h]
0x140004400  mov     rcx, [rbp+57h+var_30]
0x140004404  xor     rcx, rsp; StackCookie
0x140004407  call    __security_check_cookie
0x14000440c  lea     r11, [rsp+120h+var_20]
0x140004414  mov     rbx, [r11+38h]
0x140004418  mov     rsi, [r11+40h]
0x14000441c  mov     rsp, r11
0x14000441f  pop     r15
0x140004421  pop     r14
0x140004423  pop     r12
0x140004425  pop     rdi
0x140004426  pop     rbp
0x140004427  retn
```
