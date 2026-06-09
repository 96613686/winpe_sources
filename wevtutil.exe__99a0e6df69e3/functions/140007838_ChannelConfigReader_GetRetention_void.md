# ChannelConfigReader::GetRetention(void)

- ea: `0x140007838`
- end: `0x14000795a`
- name: `?GetRetention@ChannelConfigReader@@QEBA_NXZ`
- size: `290`
- prototype: `bool __fastcall(ChannelConfigReader *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1400073ec`

## callees

- `0x140007838`
- `0x140016284`
- `0x14001b1f8`
- `0x140022cec`
- `0x14002f6c8`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400078de`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400078de`

## pseudocode

```c
bool __fastcall ChannelConfigReader::GetRetention(ChannelConfigReader *this)
{
  ChannelConfigReader *v1; // r10
  const struct _EVT_VARIANT *Property; // rax
  bool v3; // zf
  HKEY v5; // rcx
  int v6; // ebx
  unsigned int ValueW; // edi
  const char *v8; // r8
  _BYTE pExceptionObject[56]; // [rsp+40h] [rbp-38h] BYREF
  int pvData; // [rsp+80h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+88h] [rbp+10h] BYREF

  v1 = this;
  if ( *((_BYTE *)this + 128)
    && (Property = ChannelPolicy::GetProperty(
                     (ChannelConfigReader *)((char *)this + 64),
                     EvtChannelLoggingConfigRetention)) != 0 )
  {
    v3 = !Property->BooleanVal;
  }
  else
  {
    v5 = *(HKEY *)v1;
    v6 = 1;
    if ( (unsigned int)(*((_DWORD *)v1 + 34) - 2) <= 1 )
    {
      pvData = 0;
      pcbData = 4;
      ValueW = RegGetValueW(v5, 0, L"Retention", 0x10u, 0, &pvData, &pcbData);
      if ( ValueW )
      {
        if ( ValueW != 2 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids, ValueW);
          }
          EvtException::EvtException((EvtException *)pExceptionObject, ValueW, v8, 31);
          throw (EvtException *)pExceptionObject;
        }
      }
      else
      {
        v6 = pvData;
      }
      v3 = v6 == 0;
    }
    else
    {
      v3 = (unsigned int)GetDWORDHelper(v5, 0, L"Retention") == 0;
    }
  }
  return !v3;
}

```

## disassembly

```asm
0x140007838  mov     [rsp+arg_10], rbx
0x14000783d  push    rdi
0x14000783e  sub     rsp, 70h
0x140007842  cmp     byte ptr [rcx+80h], 0
0x140007849  mov     r10, rcx
0x14000784c  jz      short loc_140007875
0x14000784e  add     rcx, 40h ; '@'; this
0x140007852  mov     edx, 6; enum _EVT_CHANNEL_CONFIG_PROPERTY_ID
0x140007857  call    ?GetProperty@ChannelPolicy@@QEBAPEBU_EVT_VARIANT@@W4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@@Z; ChannelPolicy::GetProperty(_EVT_CHANNEL_CONFIG_PROPERTY_ID)
0x14000785c  test    rax, rax
0x14000785f  jz      short loc_140007875
0x140007861  cmp     dword ptr [rax], 0
0x140007864  mov     rbx, [rsp+78h+arg_10]
0x14000786c  setnz   al
0x14000786f  add     rsp, 70h
0x140007873  pop     rdi
0x140007874  retn
0x140007875  mov     eax, [r10+88h]
0x14000787c  lea     r8, aRetention; "Retention"
0x140007883  mov     rcx, [r10]; hkey
0x140007886  sub     eax, 2
0x140007889  mov     ebx, 1
0x14000788e  cmp     eax, ebx
0x140007890  jbe     short loc_14000789D
0x140007892  xor     edx, edx
0x140007894  call    GetDWORDHelper
0x140007899  test    eax, eax
0x14000789b  jmp     short loc_140007864
0x14000789d  lea     rax, [rsp+78h+arg_8]
0x1400078a5  mov     [rsp+78h+arg_0], 0
0x1400078b0  mov     [rsp+78h+pcbData], rax; pcbData
0x1400078b5  mov     r9d, 10h; dwFlags
0x1400078bb  lea     rax, [rsp+78h+arg_0]
0x1400078c3  mov     [rsp+78h+arg_8], 4
0x1400078ce  mov     [rsp+78h+pvData], rax; pvData
0x1400078d3  xor     edx, edx; lpSubKey
0x1400078d5  mov     [rsp+78h+pdwType], 0; pdwType
0x1400078de  call    cs:__imp_RegGetValueW
0x1400078e4  mov     edi, eax
0x1400078e6  test    eax, eax
0x1400078e8  jnz     short loc_1400078F3
0x1400078ea  mov     ebx, [rsp+78h+arg_0]
0x1400078f1  jmp     short loc_1400078F8
0x1400078f3  cmp     edi, 2
0x1400078f6  jnz     short loc_1400078FF
0x1400078f8  test    ebx, ebx
0x1400078fa  jmp     loc_140007864
0x1400078ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140007906  lea     rax, WPP_GLOBAL_Control
0x14000790d  cmp     rcx, rax
0x140007910  jz      short loc_140007936
0x140007912  test    byte ptr [rcx+1Ch], 4
0x140007916  jz      short loc_140007936
0x140007918  cmp     byte ptr [rcx+19h], 2
0x14000791c  jb      short loc_140007936
0x14000791e  mov     rcx, [rcx+10h]
0x140007922  lea     r8, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids
0x140007929  mov     edx, 0Ah
0x14000792e  mov     r9d, edi
0x140007931  call    WPP_SF_d
0x140007936  mov     r9d, 1Fh; int
0x14000793c  lea     rcx, [rsp+78h+pExceptionObject]; this
0x140007941  mov     edx, edi; unsigned int
0x140007943  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140007948  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000794f  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x140007954  call    _CxxThrowException_0
```
