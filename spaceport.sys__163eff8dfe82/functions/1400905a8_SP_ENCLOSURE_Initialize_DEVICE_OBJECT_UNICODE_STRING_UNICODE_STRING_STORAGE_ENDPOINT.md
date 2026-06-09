# SP_ENCLOSURE::Initialize(_DEVICE_OBJECT *,_UNICODE_STRING *,_UNICODE_STRING *,_STORAGE_ENDPOINT *)

- ea: `0x1400905a8`
- end: `0x140090919`
- name: `?Initialize@SP_ENCLOSURE@@QEAAJPEAU_DEVICE_OBJECT@@PEAU_UNICODE_STRING@@1PEAU_STORAGE_ENDPOINT@@@Z`
- size: `881`
- prototype: `__int64 __fastcall(SP_ENCLOSURE *__hidden this, PDEVICE_OBJECT DeviceObject, PCUNICODE_STRING StringIn, PCUNICODE_STRING, struct _STORAGE_ENDPOINT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140091470`

## callees

- `0x140024a60`
- `0x14002c874`
- `0x14002ce90`
- `0x1400905a8`
- `0x140091c08`
- `0x140091c90`
- `0x140091da4`
- `0x140092158`
- `0x1400a5970`
- `0x1400b6330`

## import_xrefs

- `ntoskrnl!ExUuidCreate` at `0x14009071d`
- `ntoskrnl!ExUuidCreate` at `0x14009071d`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140090601`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140090626`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140090601`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140090626`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1400905e8`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1400905e8`

## pseudocode

```c
__int64 __fastcall SP_ENCLOSURE::Initialize(
        SP_ENCLOSURE *this,
        PDEVICE_OBJECT DeviceObject,
        PCUNICODE_STRING StringIn,
        PCUNICODE_STRING a4,
        struct _STORAGE_ENDPOINT *a5)
{
  int Size; // ebp
  bool v9; // al
  NTSTATUS Property; // edi
  int v11; // ecx
  struct _STORAGE_DEVICE_DESCRIPTOR *v12; // rcx
  int v13; // eax
  int v14; // r9d
  __int64 v15; // rdx
  __int64 i; // r8
  int v17; // ecx
  int v18; // r8d
  __int64 v19; // rcx
  __int64 j; // r10
  char v21; // al
  __int64 v22; // r8
  PWSTR Buffer; // rdx
  PWSTR v24; // rax
  ULONG DeviceType; // ecx
  const char *v26; // r9

  Size = 0;
  *((_BYTE *)this + 48) = a5 != 0;
  v9 = !a5 || *((__int64 *)a5 + 3) < 0;
  *((_BYTE *)this + 49) = v9;
  *((_QWORD *)this + 9) = IoGetAttachedDeviceReference(DeviceObject);
  Property = RtlDuplicateUnicodeString(0, a4, (PUNICODE_STRING)this + 2);
  if ( Property >= 0 )
  {
    Property = RtlDuplicateUnicodeString(0, StringIn, (PUNICODE_STRING)((char *)this + 56));
    if ( Property >= 0 )
    {
      Property = SpQueryProperty(*((PDEVICE_OBJECT *)this + 9), StorageDeviceProperty, 0x28u, (void **)this + 10);
      if ( Property >= 0 )
      {
        v12 = (struct _STORAGE_DEVICE_DESCRIPTOR *)*((_QWORD *)this + 10);
        Size = 40;
        if ( v12->Size > 0x28 )
          Size = v12->Size;
        Property = ScExtractDeviceStrings(
                     v12,
                     (struct _UNICODE_STRING *)this + 7,
                     (struct _UNICODE_STRING *)this + 8,
                     (struct _UNICODE_STRING *)this + 9,
                     (struct _UNICODE_STRING *)this + 10);
        if ( Property >= 0 )
        {
          Size = 0;
          Property = SpQueryProperty(*((PDEVICE_OBJECT *)this + 9), StorageDeviceIdProperty, 0x10u, (void **)this + 11);
          if ( Property >= 0 )
          {
            v13 = SpQueryProperty(
                    *((PDEVICE_OBJECT *)this + 9),
                    StorageDeviceFaultDomainProperty,
                    0x1Cu,
                    (void **)this + 12);
            Property = v13;
            if ( *((_BYTE *)this + 48) && v13 < 0 )
            {
              v11 = 501;
            }
            else
            {
              *((GUID *)this + 1) = GUID_NULL;
              if ( (int)SpGenerateIdByStorageId(
                          *((struct _STORAGE_DEVICE_ID_DESCRIPTOR **)this + 11),
                          (struct _GUID *)this + 1) >= 0
                || (Property = ExUuidCreate((UUID *)this + 1), Property >= 0) )
              {
                Property = SP_ENCLOSURE::UpdatePage(this, 1u);
                if ( Property >= 0 )
                {
                  SP_ENCLOSURE::UpdateRevision(this);
                  v14 = 0;
                  v15 = *((_QWORD *)this + 22) + 8LL;
                  for ( i = 0; (unsigned int)i < *(unsigned __int8 *)(*((_QWORD *)this + 22) + 10LL); v14 += v17 )
                  {
                    v17 = *(unsigned __int8 *)(v15 + *(unsigned __int8 *)(*((_QWORD *)this + 22) + 11LL) + 4 * i + 5);
                    i = (unsigned int)(i + 1);
                  }
                  *((_DWORD *)this + 50) = v14;
                  v18 = 0;
                  v19 = 0;
                  for ( j = v15 + *(unsigned __int8 *)(v15 + 3);
                        (unsigned int)v19 < *(unsigned __int8 *)(v15 + 2);
                        v19 = (unsigned int)(v19 + 1) )
                  {
                    v21 = *(_BYTE *)(j + 4 * v19 + 4);
                    if ( v21 == 1 || v21 == 23 )
                      v18 += *(unsigned __int8 *)(j + 4 * v19 + 5);
                  }
                  *((_DWORD *)this + 51) = v18;
                  Property = SP_ENCLOSURE::UpdatePage(this, 2u);
                  if ( Property >= 0 )
                  {
                    Property = SP_ENCLOSURE::UpdatePage(this, 0xAu);
                    if ( Property >= 0 )
                    {
                      SP_ENCLOSURE::UpdateHealth(this);
                      SP_ENCLOSURE::UpdateClock(this);
                      goto LABEL_51;
                    }
                    v11 = 526;
                  }
                  else
                  {
                    v11 = 523;
                  }
                }
                else
                {
                  v11 = 515;
                }
              }
              else
              {
                v11 = 507;
              }
            }
          }
          else
          {
            v11 = 493;
          }
        }
        else
        {
          v11 = 486;
        }
      }
      else
      {
        v11 = 477;
      }
    }
    else
    {
      v11 = 471;
    }
  }
  else
  {
    v11 = 466;
  }
  if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 1) != 0 )
  {
    if ( Size )
      v22 = *((_QWORD *)this + 10);
    else
      v22 = 0;
    Buffer = (PWSTR)*((_QWORD *)this + 17);
    if ( !Buffer )
      Buffer = a4->Buffer;
    v24 = (PWSTR)*((_QWORD *)this + 15);
    if ( !v24 )
      v24 = StringIn->Buffer;
    McTemplateK0jzzzzqbr5qq_EtwWriteTransfer(
      v11,
      (_DWORD)Buffer,
      v22,
      (_DWORD)this + 16,
      (__int64)v24,
      (__int64)Buffer,
      *((_QWORD *)this + 21),
      *((_QWORD *)this + 19),
      Size,
      v22,
      v11,
      Property);
  }
  if ( Property != -2147483643 && Property != -1073741789 )
  {
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 1 )
    {
      DeviceType = 1;
      WPP_MAIN_CB.DeviceType = 1;
    }
    v26 = "Error";
    goto LABEL_54;
  }
LABEL_51:
  DeviceType = WPP_MAIN_CB.DeviceType;
  if ( WPP_MAIN_CB.DeviceType != 3 )
  {
    DeviceType = 3;
    WPP_MAIN_CB.DeviceType = 3;
  }
  v26 = "Exit ";
LABEL_54:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= DeviceType )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      12,
      (unsigned int)WPP_fba83d071e923739d2c76d79c9d01cab_Traceguids,
      (_DWORD)v26,
      Property);
  }
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x1400905a8  push    rbx
0x1400905aa  push    rbp
0x1400905ab  push    rsi
0x1400905ac  push    rdi
0x1400905ad  push    r14
0x1400905af  push    r15
0x1400905b1  sub     rsp, 68h
0x1400905b5  mov     rbx, rcx
0x1400905b8  xor     ebp, ebp
0x1400905ba  mov     rcx, [rsp+98h+arg_20]
0x1400905c2  mov     r15, r9
0x1400905c5  test    rcx, rcx
0x1400905c8  mov     r14, r8
0x1400905cb  setnz   al
0x1400905ce  mov     [rbx+30h], al
0x1400905d1  test    rcx, rcx
0x1400905d4  jz      short loc_1400905E0
0x1400905d6  cmp     [rcx+18h], rbp
0x1400905da  jl      short loc_1400905E0
0x1400905dc  xor     eax, eax
0x1400905de  jmp     short loc_1400905E2
0x1400905e0  mov     al, 1
0x1400905e2  mov     rcx, rdx; DeviceObject
0x1400905e5  mov     [rbx+31h], al
0x1400905e8  call    cs:__imp_IoGetAttachedDeviceReference
0x1400905ef  nop     dword ptr [rax+rax+00h]
0x1400905f4  lea     r8, [rbx+20h]; StringOut
0x1400905f8  mov     rdx, r15; StringIn
0x1400905fb  xor     ecx, ecx; Flags
0x1400905fd  mov     [rbx+48h], rax
0x140090601  call    cs:__imp_RtlDuplicateUnicodeString
0x140090608  nop     dword ptr [rax+rax+00h]
0x14009060d  mov     edi, eax
0x14009060f  test    eax, eax
0x140090611  jns     short loc_14009061D
0x140090613  mov     ecx, 1D2h
0x140090618  jmp     loc_140090801
0x14009061d  lea     r8, [rbx+38h]; StringOut
0x140090621  mov     rdx, r14; StringIn
0x140090624  xor     ecx, ecx; Flags
0x140090626  call    cs:__imp_RtlDuplicateUnicodeString
0x14009062d  nop     dword ptr [rax+rax+00h]
0x140090632  mov     edi, eax
0x140090634  test    eax, eax
0x140090636  jns     short loc_140090642
0x140090638  mov     ecx, 1D7h
0x14009063d  jmp     loc_140090801
0x140090642  mov     rcx, [rbx+48h]; DeviceObject
0x140090646  lea     r9, [rbx+50h]; void **
0x14009064a  xor     edx, edx; enum _STORAGE_PROPERTY_ID
0x14009064c  lea     r8d, [rdx+28h]; unsigned int
0x140090650  call    ?SpQueryProperty@@YAJPEAU_DEVICE_OBJECT@@W4_STORAGE_PROPERTY_ID@@KPEAPEAX@Z; SpQueryProperty(_DEVICE_OBJECT *,_STORAGE_PROPERTY_ID,ulong,void * *)
0x140090655  mov     edi, eax
0x140090657  test    eax, eax
0x140090659  jns     short loc_140090665
0x14009065b  mov     ecx, 1DDh
0x140090660  jmp     loc_140090801
0x140090665  mov     rcx, [rbx+50h]; struct _STORAGE_DEVICE_DESCRIPTOR *
0x140090669  lea     r9, [rbx+90h]; struct _UNICODE_STRING *
0x140090670  mov     ebp, 28h ; '('
0x140090675  lea     r8, [rbx+80h]; struct _UNICODE_STRING *
0x14009067c  lea     rdx, [rbx+70h]; struct _UNICODE_STRING *
0x140090680  mov     eax, [rcx+4]
0x140090683  cmp     eax, ebp
0x140090685  cmova   ebp, eax
0x140090688  lea     rax, [rbx+0A0h]
0x14009068f  mov     [rsp+98h+var_78], rax; struct _UNICODE_STRING *
0x140090694  call    ?ScExtractDeviceStrings@@YAJPEAU_STORAGE_DEVICE_DESCRIPTOR@@PEAU_UNICODE_STRING@@111@Z; ScExtractDeviceStrings(_STORAGE_DEVICE_DESCRIPTOR *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)
0x140090699  mov     edi, eax
0x14009069b  test    eax, eax
0x14009069d  jns     short loc_1400906A9
0x14009069f  mov     ecx, 1E6h
0x1400906a4  jmp     loc_140090801
0x1400906a9  mov     rcx, [rbx+48h]; DeviceObject
0x1400906ad  lea     r9, [rbx+58h]; void **
0x1400906b1  xor     ebp, ebp
0x1400906b3  lea     edx, [rbp+2]; enum _STORAGE_PROPERTY_ID
0x1400906b6  lea     r8d, [rbp+10h]; unsigned int
0x1400906ba  call    ?SpQueryProperty@@YAJPEAU_DEVICE_OBJECT@@W4_STORAGE_PROPERTY_ID@@KPEAPEAX@Z; SpQueryProperty(_DEVICE_OBJECT *,_STORAGE_PROPERTY_ID,ulong,void * *)
0x1400906bf  mov     edi, eax
0x1400906c1  test    eax, eax
0x1400906c3  jns     short loc_1400906CF
0x1400906c5  mov     ecx, 1EDh
0x1400906ca  jmp     loc_140090801
0x1400906cf  mov     rcx, [rbx+48h]; DeviceObject
0x1400906d3  lea     r9, [rbx+60h]; void **
0x1400906d7  mov     edx, 13h; enum _STORAGE_PROPERTY_ID
0x1400906dc  lea     r8d, [rdx+9]; unsigned int
0x1400906e0  call    ?SpQueryProperty@@YAJPEAU_DEVICE_OBJECT@@W4_STORAGE_PROPERTY_ID@@KPEAPEAX@Z; SpQueryProperty(_DEVICE_OBJECT *,_STORAGE_PROPERTY_ID,ulong,void * *)
0x1400906e5  mov     edi, eax
0x1400906e7  cmp     [rbx+30h], bpl
0x1400906eb  jz      short loc_1400906FB
0x1400906ed  test    eax, eax
0x1400906ef  jns     short loc_1400906FB
0x1400906f1  mov     ecx, 1F5h
0x1400906f6  jmp     loc_140090801
0x1400906fb  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140090702  lea     rdi, [rbx+10h]
0x140090706  mov     rdx, rdi; struct _GUID *
0x140090709  movdqu  xmmword ptr [rdi], xmm0
0x14009070d  mov     rcx, [rbx+58h]; struct _STORAGE_DEVICE_ID_DESCRIPTOR *
0x140090711  call    ?SpGenerateIdByStorageId@@YAJPEAU_STORAGE_DEVICE_ID_DESCRIPTOR@@PEAU_GUID@@@Z; SpGenerateIdByStorageId(_STORAGE_DEVICE_ID_DESCRIPTOR *,_GUID *)
0x140090716  test    eax, eax
0x140090718  jns     short loc_140090739
0x14009071a  mov     rcx, rdi; Uuid
0x14009071d  call    cs:__imp_ExUuidCreate
0x140090724  nop     dword ptr [rax+rax+00h]
0x140090729  mov     edi, eax
0x14009072b  test    eax, eax
0x14009072d  jns     short loc_140090739
0x14009072f  mov     ecx, 1FBh
0x140090734  jmp     loc_140090801
0x140090739  mov     dl, 1; unsigned __int8
0x14009073b  mov     rcx, rbx; this
0x14009073e  call    ?UpdatePage@SP_ENCLOSURE@@QEAAJE@Z; SP_ENCLOSURE::UpdatePage(uchar)
0x140090743  mov     edi, eax
0x140090745  test    eax, eax
0x140090747  jns     short loc_140090753
0x140090749  mov     ecx, 203h
0x14009074e  jmp     loc_140090801
0x140090753  mov     rcx, rbx; this
0x140090756  call    ?UpdateRevision@SP_ENCLOSURE@@QEAAXXZ; SP_ENCLOSURE::UpdateRevision(void)
0x14009075b  mov     rdx, [rbx+0B0h]
0x140090762  xor     r9d, r9d
0x140090765  add     rdx, 8
0x140090769  xor     r8d, r8d
0x14009076c  movzx   r10d, byte ptr [rdx+3]
0x140090771  movzx   r11d, byte ptr [rdx+2]
0x140090776  add     r10, rdx
0x140090779  test    r11d, r11d
0x14009077c  jz      short loc_14009078F
0x14009077e  movzx   ecx, byte ptr [r10+r8*4+5]
0x140090784  inc     r8d
0x140090787  add     r9d, ecx
0x14009078a  cmp     r8d, r11d
0x14009078d  jb      short loc_14009077E
0x14009078f  mov     [rbx+0C8h], r9d
0x140090796  xor     r8d, r8d
0x140090799  movzx   r10d, byte ptr [rdx+3]
0x14009079e  xor     ecx, ecx
0x1400907a0  movzx   r11d, byte ptr [rdx+2]
0x1400907a5  add     r10, rdx
0x1400907a8  test    r11d, r11d
0x1400907ab  jz      short loc_1400907CA
0x1400907ad  mov     al, [r10+rcx*4+4]
0x1400907b2  cmp     al, 1
0x1400907b4  jz      short loc_1400907BA
0x1400907b6  cmp     al, 17h
0x1400907b8  jnz     short loc_1400907C3
0x1400907ba  movzx   eax, byte ptr [r10+rcx*4+5]
0x1400907c0  add     r8d, eax
0x1400907c3  inc     ecx
0x1400907c5  cmp     ecx, r11d
0x1400907c8  jb      short loc_1400907AD
0x1400907ca  mov     dl, 2; unsigned __int8
0x1400907cc  mov     [rbx+0CCh], r8d
0x1400907d3  mov     rcx, rbx; this
0x1400907d6  call    ?UpdatePage@SP_ENCLOSURE@@QEAAJE@Z; SP_ENCLOSURE::UpdatePage(uchar)
0x1400907db  mov     edi, eax
0x1400907dd  test    eax, eax
0x1400907df  jns     short loc_1400907E8
0x1400907e1  mov     ecx, 20Bh
0x1400907e6  jmp     short loc_140090801
0x1400907e8  mov     dl, 0Ah; unsigned __int8
0x1400907ea  mov     rcx, rbx; this
0x1400907ed  call    ?UpdatePage@SP_ENCLOSURE@@QEAAJE@Z; SP_ENCLOSURE::UpdatePage(uchar)
0x1400907f2  mov     edi, eax
0x1400907f4  test    eax, eax
0x1400907f6  jns     loc_14009089F
0x1400907fc  mov     ecx, 20Eh
0x140090801  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 1
0x140090808  jz      short loc_140090870
0x14009080a  test    ebp, ebp
0x14009080c  jz      short loc_140090814
0x14009080e  mov     r8, [rbx+50h]
0x140090812  jmp     short loc_140090817
0x140090814  xor     r8d, r8d
0x140090817  mov     rdx, [rbx+88h]
0x14009081e  mov     r10, [rbx+98h]
0x140090825  mov     r11, [rbx+0A8h]
0x14009082c  test    rdx, rdx
0x14009082f  jnz     short loc_140090835
0x140090831  mov     rdx, [r15+8]
0x140090835  mov     rax, [rbx+78h]
0x140090839  test    rax, rax
0x14009083c  jnz     short loc_140090842
0x14009083e  mov     rax, [r14+8]
0x140090842  mov     [rsp+98h+var_40], edi
0x140090846  lea     r9, [rbx+10h]
0x14009084a  mov     [rsp+98h+var_48], ecx
0x14009084e  mov     [rsp+98h+var_50], r8
0x140090853  mov     [rsp+98h+var_58], ebp
0x140090857  mov     [rsp+98h+var_60], r10
0x14009085c  mov     [rsp+98h+var_68], r11
0x140090861  mov     [rsp+98h+var_70], rdx
0x140090866  mov     [rsp+98h+var_78], rax
0x14009086b  call    McTemplateK0jzzzzqbr5qq_EtwWriteTransfer
0x140090870  cmp     edi, 80000005h
0x140090876  jz      short loc_1400908AF
0x140090878  cmp     edi, 0C0000023h
0x14009087e  jz      short loc_1400908AF
0x140090880  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x140090886  cmp     ecx, 1
0x140090889  jz      short loc_140090896
0x14009088b  mov     ecx, 1
0x140090890  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x140090896  lea     r9, aError; "Error"
0x14009089d  jmp     short loc_1400908CC
0x14009089f  mov     rcx, rbx; this
0x1400908a2  call    ?UpdateHealth@SP_ENCLOSURE@@QEAAXXZ; SP_ENCLOSURE::UpdateHealth(void)
0x1400908a7  mov     rcx, rbx; this
0x1400908aa  call    ?UpdateClock@SP_ENCLOSURE@@QEAAXXZ; SP_ENCLOSURE::UpdateClock(void)
0x1400908af  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400908b5  cmp     ecx, 3
0x1400908b8  jz      short loc_1400908C5
0x1400908ba  mov     ecx, 3
0x1400908bf  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400908c5  lea     r9, aExit; "Exit "
0x1400908cc  mov     r10, cs:WPP_GLOBAL_Control
0x1400908d3  lea     rax, WPP_GLOBAL_Control
0x1400908da  cmp     r10, rax
0x1400908dd  jz      short loc_140090909
0x1400908df  mov     eax, [r10+2Ch]
0x1400908e3  test    al, 1
0x1400908e5  jz      short loc_140090909
0x1400908e7  movzx   eax, byte ptr [r10+29h]
0x1400908ec  cmp     eax, ecx
0x1400908ee  jb      short loc_140090909
0x1400908f0  mov     rcx, [r10+18h]
0x1400908f4  lea     r8, WPP_fba83d071e923739d2c76d79c9d01cab_Traceguids
0x1400908fb  mov     edx, 0Ch
0x140090900  mov     dword ptr [rsp+98h+var_78], edi
0x140090904  call    WPP_SF_sd
0x140090909  mov     eax, edi
0x14009090b  add     rsp, 68h
0x14009090f  pop     r15
0x140090911  pop     r14
0x140090913  pop     rdi
0x140090914  pop     rsi
0x140090915  pop     rbp
0x140090916  pop     rbx
0x140090917  retn
```
