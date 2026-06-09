# StartRoutine

- ea: `0x140014d80`
- end: `0x14001525d`
- name: `StartRoutine`
- size: `1245`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x140001008`
- `0x14000414c`
- `0x140005374`
- `0x140014d80`
- `0x140016a40`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x140014e4e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140014e4e`
- `ntoskrnl!ObfDereferenceObject` at `0x140014ed9`
- `ntoskrnl!ObfDereferenceObject` at `0x140015205`
- `ntoskrnl!ObfDereferenceObject` at `0x140014ed9`
- `ntoskrnl!ObfDereferenceObject` at `0x140015205`
- `ntoskrnl!KeResetEvent` at `0x140015199`
- `ntoskrnl!KeResetEvent` at `0x140015199`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140014f8c`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140014f8c`
- `ntoskrnl!PsTerminateSystemThread` at `0x140014dea`
- `ntoskrnl!PsTerminateSystemThread` at `0x140014e1f`
- `ntoskrnl!PsTerminateSystemThread` at `0x140014e73`
- `ntoskrnl!PsTerminateSystemThread` at `0x140014ef8`
- `ntoskrnl!PsTerminateSystemThread` at `0x140015224`
- `ntoskrnl!PsTerminateSystemThread` at `0x140014dea`
- `ntoskrnl!PsTerminateSystemThread` at `0x140014e1f`
- `ntoskrnl!PsTerminateSystemThread` at `0x140014e73`
- `ntoskrnl!PsTerminateSystemThread` at `0x140014ef8`
- `ntoskrnl!PsTerminateSystemThread` at `0x140015224`
- `ntoskrnl!ZwNotifyChangeKey` at `0x140014f49`
- `ntoskrnl!ZwNotifyChangeKey` at `0x1400151d9`
- `ntoskrnl!ZwNotifyChangeKey` at `0x140014f49`
- `ntoskrnl!ZwNotifyChangeKey` at `0x1400151d9`
- `ntoskrnl!ZwCreateEvent` at `0x140014e0d`
- `ntoskrnl!ZwCreateEvent` at `0x140014e0d`
- `ntoskrnl!ExEventObjectType` at `0x140014e2b`
- `ntoskrnl!ZwCreateKey` at `0x140014ec2`
- `ntoskrnl!ZwCreateKey` at `0x140014ec2`
- `ntoskrnl!ZwClose` at `0x140014e65`
- `ntoskrnl!ZwClose` at `0x140014eea`
- `ntoskrnl!ZwClose` at `0x1400151f4`
- `ntoskrnl!ZwClose` at `0x140015216`
- `ntoskrnl!ZwClose` at `0x140014e65`
- `ntoskrnl!ZwClose` at `0x140014eea`
- `ntoskrnl!ZwClose` at `0x1400151f4`
- `ntoskrnl!ZwClose` at `0x140015216`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015188`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015188`

## pseudocode

```c
void __fastcall StartRoutine(PUNICODE_STRING *StartContext)
{
  int v2; // eax
  int v3; // ebx
  int v4; // ebx
  int v5; // ebx
  NTSTATUS v6; // eax
  PUNICODE_STRING v7; // rdx
  PUNICODE_STRING v8; // rcx
  char *v9; // rdx
  struct _EVENT_DATA_DESCRIPTOR *v10; // rax
  void *EventHandle; // [rsp+58h] [rbp-B0h] BYREF
  PVOID P; // [rsp+60h] [rbp-A8h] BYREF
  PVOID Object; // [rsp+68h] [rbp-A0h] BYREF
  void *KeyHandle; // [rsp+70h] [rbp-98h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-90h] BYREF
  int v16; // [rsp+A8h] [rbp-60h] BYREF
  unsigned int v17; // [rsp+ACh] [rbp-5Ch] BYREF
  __int64 v18; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v19; // [rsp+B8h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C0h] [rbp-48h] BYREF
  PVOID v21[3]; // [rsp+D0h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+E8h] [rbp-20h] BYREF
  __int64 *v23; // [rsp+108h] [rbp+0h]
  __int64 v24; // [rsp+110h] [rbp+8h]
  __int64 *v25; // [rsp+118h] [rbp+10h]
  __int64 v26; // [rsp+120h] [rbp+18h]
  const char *v27; // [rsp+128h] [rbp+20h]
  __int64 v28; // [rsp+130h] [rbp+28h]
  char v29; // [rsp+138h] [rbp+30h] BYREF
  __int64 *v30; // [rsp+158h] [rbp+50h]
  __int64 v31; // [rsp+160h] [rbp+58h]
  __int64 *v32; // [rsp+168h] [rbp+60h]
  __int64 v33; // [rsp+170h] [rbp+68h]
  const char *v34; // [rsp+178h] [rbp+70h]
  __int64 v35; // [rsp+180h] [rbp+78h]

  KeyHandle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  EventHandle = 0;
  Object = 0;
  IoStatusBlock = 0;
  if ( !StartContext || !*StartContext || !StartContext[1] )
    PsTerminateSystemThread(-1073741811);
  v2 = ZwCreateEvent(&EventHandle, 0x1F0003u, 0, NotificationEvent, 0);
  if ( v2 < 0 )
    PsTerminateSystemThread(v2);
  v3 = ObReferenceObjectByHandle(EventHandle, 0x1F0003u, (POBJECT_TYPE)ExEventObjectType, 0, &Object, 0);
  if ( v3 < 0 )
  {
    ZwClose(EventHandle);
    PsTerminateSystemThread(v3);
  }
  ObjectAttributes.ObjectName = *StartContext;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  v4 = ZwCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, 0);
  if ( v4 < 0 )
  {
    ObfDereferenceObject(Object);
    ZwClose(EventHandle);
    PsTerminateSystemThread(v4);
  }
  v21[0] = Object;
  v21[1] = StartContext + 3;
  v5 = ZwNotifyChangeKey(KeyHandle, EventHandle, 0, 0, &IoStatusBlock, 4u, 0, 0, 0, 1u);
  if ( v5 >= 0 )
  {
    while ( 1 )
    {
      v6 = KeWaitForMultipleObjects(2u, v21, WaitAny, Executive, 0, 0, 0, 0);
      v5 = v6;
      if ( v6 < 0 || v6 == 1 )
        goto LABEL_33;
      v7 = StartContext[1];
      v8 = *StartContext;
      P = 0;
      v16 = 0;
      v17 = 0;
      if ( (int)sub_140005374(v8, v7, &v16, &P, &v17) >= 0 )
        break;
LABEL_32:
      KeResetEvent((PRKEVENT)Object);
      v5 = ZwNotifyChangeKey(KeyHandle, EventHandle, 0, 0, &IoStatusBlock, 4u, 0, 0, 0, 1u);
      if ( v5 < 0 )
        goto LABEL_33;
    }
    if ( *((_DWORD *)StartContext + 4) == v16 )
    {
      switch ( v16 )
      {
        case 1:
          if ( (dword_140021754 & 0x4000000) != 0 && byte_140021770 )
            sub_14000414C(P, v17);
          goto LABEL_31;
        case 4:
          dword_140021754 = *(_DWORD *)P;
          if ( (unsigned int)dword_140021000 <= 5
            || (qword_140021010 & 0x400000000000LL) == 0
            || (qword_140021018 & 0x400000000000LL) != qword_140021018 )
          {
            goto LABEL_31;
          }
          v19 = 0x1000000;
          v30 = &v19;
          v9 = (char *)&qword_14001F908;
          v31 = 8;
          LODWORD(v18) = dword_140021754;
          v32 = &v18;
          v34 = "4.6.0.0";
          v10 = (struct _EVENT_DATA_DESCRIPTOR *)&v29;
          v33 = 4;
          v35 = 8;
          break;
        case 11:
          qword_140021740 = *(_QWORD *)P;
          if ( (unsigned int)dword_140021000 <= 5
            || (qword_140021010 & 0x400000000000LL) == 0
            || (qword_140021018 & 0x400000000000LL) != qword_140021018 )
          {
            goto LABEL_31;
          }
          v18 = 0x1000000;
          v23 = &v18;
          v9 = &byte_14001F94F;
          v24 = 8;
          v19 = qword_140021740;
          v25 = &v19;
          v27 = "4.6.0.0";
          v10 = &v22;
          v26 = 8;
          v28 = 8;
          break;
        default:
          goto LABEL_31;
      }
      sub_140001008((int)&dword_140021000, (int)v9, 0, 0, 5u, v10);
    }
LABEL_31:
    ExFreePoolWithTag(P, 0);
    goto LABEL_32;
  }
LABEL_33:
  ZwClose(KeyHandle);
  ObfDereferenceObject(Object);
  ZwClose(EventHandle);
  PsTerminateSystemThread(v5);
}

```

## disassembly

```asm
0x140014d80  mov     rax, rsp
0x140014d83  mov     [rax+10h], rbx
0x140014d87  mov     [rax+18h], rsi
0x140014d8b  mov     [rax+20h], rdi
0x140014d8f  push    rbp
0x140014d90  push    r14
0x140014d92  push    r15
0x140014d94  lea     rbp, [rax-0A8h]
0x140014d9b  sub     rsp, 190h
0x140014da2  mov     rax, cs:__security_cookie
0x140014da9  xor     rax, rsp
0x140014dac  mov     [rbp+0A0h+var_20], rax
0x140014db3  xor     esi, esi
0x140014db5  xorps   xmm0, xmm0
0x140014db8  mov     [rsp+1A0h+KeyHandle], rsi
0x140014dbd  mov     rdi, rcx
0x140014dc0  mov     dword ptr [rsp+1A0h+ObjectAttributes+4], esi
0x140014dc4  mov     dword ptr [rbp+0A0h+ObjectAttributes+1Ch], esi
0x140014dc7  mov     [rsp+1A0h+EventHandle], rsi
0x140014dcc  mov     [rsp+1A0h+Object], rsi
0x140014dd1  movups  xmmword ptr [rbp+0A0h+IoStatusBlock], xmm0
0x140014dd5  test    rcx, rcx
0x140014dd8  jz      short loc_140014DE5
0x140014dda  cmp     [rcx], rsi
0x140014ddd  jz      short loc_140014DE5
0x140014ddf  cmp     [rcx+8], rsi
0x140014de3  jnz     short loc_140014DF6
0x140014de5  mov     ecx, 0C000000Dh; ExitStatus
0x140014dea  call    cs:PsTerminateSystemThread
0x140014df1  nop     dword ptr [rax+rax+00h]
0x140014df6  mov     ebx, 1F0003h
0x140014dfb  mov     [rsp+1A0h+InitialState], sil; InitialState
0x140014e00  mov     edx, ebx; DesiredAccess
0x140014e02  lea     rcx, [rsp+1A0h+EventHandle]; EventHandle
0x140014e07  xor     r9d, r9d; EventType
0x140014e0a  xor     r8d, r8d; ObjectAttributes
0x140014e0d  call    cs:ZwCreateEvent
0x140014e14  nop     dword ptr [rax+rax+00h]
0x140014e19  test    eax, eax
0x140014e1b  jns     short loc_140014E2B
0x140014e1d  mov     ecx, eax; ExitStatus
0x140014e1f  call    cs:PsTerminateSystemThread
0x140014e26  nop     dword ptr [rax+rax+00h]
0x140014e2b  mov     r8, cs:ExEventObjectType
0x140014e32  lea     rax, [rsp+1A0h+Object]
0x140014e37  mov     rcx, [rsp+1A0h+EventHandle]; Handle
0x140014e3c  xor     r9d, r9d; AccessMode
0x140014e3f  mov     [rsp+1A0h+HandleInformation], rsi; HandleInformation
0x140014e44  mov     edx, ebx; DesiredAccess
0x140014e46  mov     qword ptr [rsp+1A0h+InitialState], rax; Object
0x140014e4b  mov     r8, [r8]; ObjectType
0x140014e4e  call    cs:ObReferenceObjectByHandle
0x140014e55  nop     dword ptr [rax+rax+00h]
0x140014e5a  mov     ebx, eax
0x140014e5c  test    eax, eax
0x140014e5e  jns     short loc_140014E7F
0x140014e60  mov     rcx, [rsp+1A0h+EventHandle]; Handle
0x140014e65  call    cs:ZwClose
0x140014e6c  nop     dword ptr [rax+rax+00h]
0x140014e71  mov     ecx, ebx; ExitStatus
0x140014e73  call    cs:PsTerminateSystemThread
0x140014e7a  nop     dword ptr [rax+rax+00h]
0x140014e7f  mov     rax, [rdi]
0x140014e82  lea     r8, [rsp+1A0h+ObjectAttributes]; ObjectAttributes
0x140014e87  xorps   xmm0, xmm0
0x140014e8a  mov     [rsp+1A0h+Disposition], rsi; Disposition
0x140014e8f  mov     dword ptr [rsp+1A0h+HandleInformation], esi; CreateOptions
0x140014e93  lea     rcx, [rsp+1A0h+KeyHandle]; KeyHandle
0x140014e98  xor     r9d, r9d; TitleIndex
0x140014e9b  mov     [rbp+0A0h+ObjectAttributes.ObjectName], rax
0x140014e9f  mov     edx, 0F003Fh; DesiredAccess
0x140014ea4  mov     qword ptr [rsp+1A0h+InitialState], rsi; Class
0x140014ea9  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140014eae  mov     [rsp+1A0h+ObjectAttributes.Length], 30h ; '0'
0x140014eb6  mov     [rsp+1A0h+ObjectAttributes.RootDirectory], rsi
0x140014ebb  mov     [rbp+0A0h+ObjectAttributes.Attributes], 240h
0x140014ec2  call    cs:ZwCreateKey
0x140014ec9  nop     dword ptr [rax+rax+00h]
0x140014ece  mov     ebx, eax
0x140014ed0  test    eax, eax
0x140014ed2  jns     short loc_140014F04
0x140014ed4  mov     rcx, [rsp+1A0h+Object]; Object
0x140014ed9  call    cs:ObfDereferenceObject
0x140014ee0  nop     dword ptr [rax+rax+00h]
0x140014ee5  mov     rcx, [rsp+1A0h+EventHandle]; Handle
0x140014eea  call    cs:ZwClose
0x140014ef1  nop     dword ptr [rax+rax+00h]
0x140014ef6  mov     ecx, ebx; ExitStatus
0x140014ef8  call    cs:PsTerminateSystemThread
0x140014eff  nop     dword ptr [rax+rax+00h]
0x140014f04  mov     rax, [rsp+1A0h+Object]
0x140014f09  xor     r9d, r9d; ApcContext
0x140014f0c  mov     rdx, [rsp+1A0h+EventHandle]; Event
0x140014f11  xor     r8d, r8d; ApcRoutine
0x140014f14  mov     rcx, [rsp+1A0h+KeyHandle]; KeyHandle
0x140014f19  mov     [rsp+1A0h+Asynchronous], 1; Asynchronous
0x140014f1e  mov     [rsp+1A0h+BufferSize], esi; BufferSize
0x140014f22  mov     [rbp+0A0h+var_D8], rax
0x140014f26  lea     rax, [rdi+18h]
0x140014f2a  mov     [rsp+1A0h+Buffer], rsi; Buffer
0x140014f2f  mov     [rbp+0A0h+var_D0], rax
0x140014f33  lea     rax, [rbp+0A0h+IoStatusBlock]
0x140014f37  mov     byte ptr [rsp+1A0h+Disposition], sil; WatchTree
0x140014f3c  mov     dword ptr [rsp+1A0h+HandleInformation], 4; CompletionFilter
0x140014f44  mov     qword ptr [rsp+1A0h+InitialState], rax; IoStatusBlock
0x140014f49  call    cs:ZwNotifyChangeKey
0x140014f50  nop     dword ptr [rax+rax+00h]
0x140014f55  mov     ebx, eax
0x140014f57  test    eax, eax
0x140014f59  js      loc_1400151EF
0x140014f5f  mov     r14, 400000000000h
0x140014f69  xor     r9d, r9d; WaitReason
0x140014f6c  mov     [rsp+1A0h+Buffer], rsi; WaitBlockArray
0x140014f71  mov     [rsp+1A0h+Disposition], rsi; Timeout
0x140014f76  lea     rdx, [rbp+0A0h+var_D8]; Object
0x140014f7a  mov     byte ptr [rsp+1A0h+HandleInformation], sil; Alertable
0x140014f7f  mov     [rsp+1A0h+InitialState], sil; WaitMode
0x140014f84  lea     r8d, [r9+1]; WaitType
0x140014f88  lea     ecx, [r9+2]; Count
0x140014f8c  call    cs:KeWaitForMultipleObjects
0x140014f93  nop     dword ptr [rax+rax+00h]
0x140014f98  mov     ebx, eax
0x140014f9a  test    eax, eax
0x140014f9c  js      loc_1400151EF
0x140014fa2  cmp     eax, 1
0x140014fa5  jz      loc_1400151EF
0x140014fab  mov     rdx, [rdi+8]
0x140014faf  lea     rax, [rbp+0A0h+var_FC]
0x140014fb3  mov     rcx, [rdi]
0x140014fb6  lea     r9, [rsp+1A0h+P]
0x140014fbb  lea     r8, [rbp+0A0h+var_100]
0x140014fbf  mov     qword ptr [rsp+1A0h+InitialState], rax
0x140014fc4  mov     [rsp+1A0h+P], rsi
0x140014fc9  mov     [rbp+0A0h+var_100], esi
0x140014fcc  mov     [rbp+0A0h+var_FC], esi
0x140014fcf  call    sub_140005374
0x140014fd4  test    eax, eax
0x140014fd6  js      loc_140015194
0x140014fdc  mov     eax, [rbp+0A0h+var_100]
0x140014fdf  cmp     [rdi+10h], eax
0x140014fe2  jnz     loc_140015181
0x140014fe8  sub     eax, 1
0x140014feb  jz      loc_14001515F
0x140014ff1  sub     eax, 3
0x140014ff4  jz      loc_1400150A7
0x140014ffa  cmp     eax, 7
0x140014ffd  jnz     loc_140015181
0x140015003  mov     rax, [rsp+1A0h+P]
0x140015008  mov     rcx, [rax]
0x14001500b  mov     eax, cs:dword_140021754
0x140015011  mov     r10, cs:off_140019010
0x140015018  mov     cs:qword_140021740, rcx
0x14001501f  cmp     dword ptr [r10], 5
0x140015023  jbe     loc_140015181
0x140015029  test    [r10+10h], r14
0x14001502d  jz      loc_140015181
0x140015033  mov     rcx, [r10+18h]
0x140015037  mov     rax, rcx
0x14001503a  and     rax, r14
0x14001503d  cmp     rax, rcx
0x140015040  jnz     loc_140015181
0x140015046  lea     rax, [rbp+0A0h+var_F8]
0x14001504a  mov     [rbp+0A0h+var_F8], 1000000h
0x140015052  mov     [rbp+0A0h+var_A0], rax
0x140015056  lea     rdx, byte_14001F94F
0x14001505d  mov     eax, cs:dword_140021754
0x140015063  shr     eax, 1Fh
0x140015066  test    al, al
0x140015068  mov     [rbp+0A0h+var_98], 8
0x140015070  mov     rax, cs:qword_140021740
0x140015077  mov     [rbp+0A0h+var_F0], rax
0x14001507b  lea     rax, [rbp+0A0h+var_F0]
0x14001507f  mov     [rbp+0A0h+var_90], rax
0x140015083  lea     rax, a4600; "4.6.0.0"
0x14001508a  mov     [rbp+0A0h+var_80], rax
0x14001508e  lea     rax, [rbp+0A0h+var_C0]
0x140015092  mov     [rbp+0A0h+var_88], 8
0x14001509a  mov     [rbp+0A0h+var_78], 8
0x1400150a2  jmp     loc_140015142
0x1400150a7  mov     rax, [rsp+1A0h+P]
0x1400150ac  mov     ecx, [rax]
0x1400150ae  mov     eax, cs:dword_140021754
0x1400150b4  mov     r10, cs:off_140019010
0x1400150bb  mov     cs:dword_140021754, ecx
0x1400150c1  cmp     dword ptr [r10], 5
0x1400150c5  jbe     loc_140015181
0x1400150cb  test    [r10+10h], r14
0x1400150cf  jz      loc_140015181
0x1400150d5  mov     rcx, [r10+18h]
0x1400150d9  mov     rax, rcx
0x1400150dc  and     rax, r14
0x1400150df  cmp     rax, rcx
0x1400150e2  jnz     loc_140015181
0x1400150e8  lea     rax, [rbp+0A0h+var_F0]
0x1400150ec  mov     [rbp+0A0h+var_F0], 1000000h
0x1400150f4  mov     [rbp+0A0h+var_50], rax
0x1400150f8  lea     rdx, qword_14001F908; int
0x1400150ff  mov     eax, cs:dword_140021754
0x140015105  shr     eax, 1Fh
0x140015108  test    al, al
0x14001510a  mov     [rbp+0A0h+var_48], 8
0x140015112  mov     eax, cs:dword_140021754
0x140015118  mov     dword ptr [rbp+0A0h+var_F8], eax
0x14001511b  lea     rax, [rbp+0A0h+var_F8]
0x14001511f  mov     [rbp+0A0h+var_40], rax
0x140015123  lea     rax, a4600; "4.6.0.0"
0x14001512a  mov     [rbp+0A0h+var_30], rax
0x14001512e  lea     rax, [rbp+0A0h+var_70]
0x140015132  mov     [rbp+0A0h+var_38], 4
0x14001513a  mov     [rbp+0A0h+var_28], 8
0x140015142  mov     [rsp+1A0h+HandleInformation], rax; PEVENT_DATA_DESCRIPTOR
0x140015147  xor     r9d, r9d; int
0x14001514a  xor     r8d, r8d; int
0x14001514d  mov     dword ptr [rsp+1A0h+InitialState], 5; ULONG
0x140015155  mov     rcx, r10; int
0x140015158  call    sub_140001008
0x14001515d  jmp     short loc_140015181
0x14001515f  mov     eax, cs:dword_140021754
0x140015165  bt      eax, 1Ah
0x140015169  jnb     short loc_140015181
0x14001516b  cmp     cs:byte_140021770, sil
0x140015172  jz      short loc_140015181
0x140015174  mov     edx, [rbp+0A0h+var_FC]
0x140015177  mov     rcx, [rsp+1A0h+P]
0x14001517c  call    sub_14000414C
0x140015181  mov     rcx, [rsp+1A0h+P]; P
0x140015186  xor     edx, edx; Tag
0x140015188  call    cs:ExFreePoolWithTag
0x14001518f  nop     dword ptr [rax+rax+00h]
0x140015194  mov     rcx, [rsp+1A0h+Object]; Event
0x140015199  call    cs:KeResetEvent
0x1400151a0  nop     dword ptr [rax+rax+00h]
0x1400151a5  mov     rdx, [rsp+1A0h+EventHandle]; Event
0x1400151aa  lea     rax, [rbp+0A0h+IoStatusBlock]
0x1400151ae  mov     rcx, [rsp+1A0h+KeyHandle]; KeyHandle
0x1400151b3  xor     r9d, r9d; ApcContext
0x1400151b6  mov     [rsp+1A0h+Asynchronous], 1; Asynchronous
0x1400151bb  xor     r8d, r8d; ApcRoutine
0x1400151be  mov     [rsp+1A0h+BufferSize], esi; BufferSize
0x1400151c2  mov     [rsp+1A0h+Buffer], rsi; Buffer
0x1400151c7  mov     byte ptr [rsp+1A0h+Disposition], sil; WatchTree
0x1400151cc  mov     dword ptr [rsp+1A0h+HandleInformation], 4; CompletionFilter
0x1400151d4  mov     qword ptr [rsp+1A0h+InitialState], rax; IoStatusBlock
0x1400151d9  call    cs:ZwNotifyChangeKey
0x1400151e0  nop     dword ptr [rax+rax+00h]
0x1400151e5  mov     ebx, eax
0x1400151e7  test    eax, eax
0x1400151e9  jns     loc_140014F69
0x1400151ef  mov     rcx, [rsp+1A0h+KeyHandle]; Handle
0x1400151f4  call    cs:ZwClose
0x1400151fb  nop     dword ptr [rax+rax+00h]
0x140015200  mov     rcx, [rsp+1A0h+Object]; Object
0x140015205  call    cs:ObfDereferenceObject
0x14001520c  nop     dword ptr [rax+rax+00h]
0x140015211  mov     rcx, [rsp+1A0h+EventHandle]; Handle
0x140015216  call    cs:ZwClose
0x14001521d  nop     dword ptr [rax+rax+00h]
0x140015222  mov     ecx, ebx; ExitStatus
0x140015224  call    cs:PsTerminateSystemThread
0x14001522b  nop     dword ptr [rax+rax+00h]
0x140015230  mov     rcx, [rbp+0A0h+var_20]
0x140015237  xor     rcx, rsp; StackCookie
0x14001523a  call    __security_check_cookie
0x14001523f  lea     r11, [rsp+1A0h+var_10]
0x140015247  mov     rbx, [r11+28h]
0x14001524b  mov     rsi, [r11+30h]
0x14001524f  mov     rdi, [r11+38h]
0x140015253  mov     rsp, r11
0x140015256  pop     r15
0x140015258  pop     r14
0x14001525a  pop     rbp
0x14001525b  retn
```
