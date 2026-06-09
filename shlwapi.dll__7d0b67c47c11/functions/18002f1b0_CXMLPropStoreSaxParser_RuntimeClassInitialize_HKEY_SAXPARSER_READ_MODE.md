# CXMLPropStoreSaxParser::RuntimeClassInitialize(HKEY__ *,SAXPARSER_READ_MODE)

- ea: `0x18002f1b0`
- end: `0x18002f2a6`
- name: `?RuntimeClassInitialize@CXMLPropStoreSaxParser@@QEAAJPEAUHKEY__@@W4SAXPARSER_READ_MODE@@@Z`
- size: `246`
- prototype: `int __high(HKEY, enum SAXPARSER_READ_MODE)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18002ce04`

## callees

- `0x18000eaf0`
- `0x18001142c`
- `0x18002f1b0`
- `0x18002f2ac`
- `0x180032030`
- `0x180036000`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002f24f`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002f274`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002f24f`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002f274`

## pseudocode

```c
__int64 __fastcall CXMLPropStoreSaxParser::RuntimeClassInitialize(__int64 a1, HKEY a2, int a3)
{
  __int64 result; // rax
  unsigned int *v7; // r8
  HDPA v8; // rax
  HANDLE Event; // rax
  HANDLE v10; // rax

  *(_DWORD *)(a1 + 120) = a3;
  result = CXMLPropStoreSaxParser::_InitializeResultDPA((CXMLPropStoreSaxParser *)a1, a2);
  if ( (int)result >= 0 )
  {
    result = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeFromRegistry(
               (BYTE **)(a1 + 40),
               a2,
               L"Schema");
    if ( (int)result >= 0 )
    {
      result = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeFromRegistry(
                 (BYTE **)(a1 + 64),
                 a2,
                 L"Namespace");
      if ( (int)result >= 0 )
      {
        *(_BYTE *)(a1 + 125) = (unsigned int)SHRegValueExists(a2, L"ResourceStrings", v7) != 0;
        v8 = DPA_Create(5);
        *(_QWORD *)(a1 + 112) = v8;
        if ( v8 )
        {
          result = 0;
          if ( a3 == 1 )
          {
            Event = CreateEventExW(0, 0, 0, 0x1F0003u);
            *(_QWORD *)(a1 + 136) = Event;
            if ( Event || (result = ResultFromKnownLastError(), (int)result >= 0) )
            {
              v10 = CreateEventExW(0, 0, 0, 0x1F0003u);
              *(_QWORD *)(a1 + 144) = v10;
              if ( v10 )
                return 0;
              else
                return ResultFromKnownLastError();
            }
          }
        }
        else
        {
          return 2147942414LL;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002f1b0  mov     [rsp+arg_0], rbx
0x18002f1b5  mov     [rsp+arg_8], rsi
0x18002f1ba  push    rdi
0x18002f1bb  sub     rsp, 20h
0x18002f1bf  mov     esi, r8d
0x18002f1c2  mov     [rcx+78h], r8d
0x18002f1c6  mov     rdi, rdx
0x18002f1c9  mov     rbx, rcx
0x18002f1cc  call    ?_InitializeResultDPA@CXMLPropStoreSaxParser@@AEAAJPEAUHKEY__@@@Z; CXMLPropStoreSaxParser::_InitializeResultDPA(HKEY__ *)
0x18002f1d1  test    eax, eax
0x18002f1d3  js      loc_18002F296
0x18002f1d9  lea     rcx, [rbx+28h]
0x18002f1dd  mov     rdx, rdi
0x18002f1e0  lea     r8, aSchema; "Schema"
0x18002f1e7  call    ?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x18002f1ec  test    eax, eax
0x18002f1ee  js      loc_18002F296
0x18002f1f4  lea     rcx, [rbx+40h]
0x18002f1f8  mov     rdx, rdi
0x18002f1fb  lea     r8, aNamespace; "Namespace"
0x18002f202  call    ?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x18002f207  test    eax, eax
0x18002f209  js      loc_18002F296
0x18002f20f  lea     rdx, aResourcestring; "ResourceStrings"
0x18002f216  mov     rcx, rdi; HKEY
0x18002f219  call    ?SHRegValueExists@@YAHPEAUHKEY__@@PEBGPEAK@Z; SHRegValueExists(HKEY__ *,ushort const *,ulong *)
0x18002f21e  test    eax, eax
0x18002f220  mov     ecx, 5; cItemGrow
0x18002f225  setnz   al
0x18002f228  mov     [rbx+7Dh], al
0x18002f22b  call    DPA_Create
0x18002f230  mov     [rbx+70h], rax
0x18002f234  test    rax, rax
0x18002f237  jz      short loc_18002F291
0x18002f239  xor     eax, eax
0x18002f23b  cmp     esi, 1
0x18002f23e  jnz     short loc_18002F296
0x18002f240  mov     edi, 1F0003h
0x18002f245  xor     r8d, r8d; dwFlags
0x18002f248  mov     r9d, edi; dwDesiredAccess
0x18002f24b  xor     edx, edx; lpName
0x18002f24d  xor     ecx, ecx; lpEventAttributes
0x18002f24f  call    cs:__imp_CreateEventExW
0x18002f255  mov     [rbx+88h], rax
0x18002f25c  test    rax, rax
0x18002f25f  jnz     short loc_18002F26A
0x18002f261  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002f266  test    eax, eax
0x18002f268  js      short loc_18002F296
0x18002f26a  mov     r9d, edi; dwDesiredAccess
0x18002f26d  xor     r8d, r8d; dwFlags
0x18002f270  xor     edx, edx; lpName
0x18002f272  xor     ecx, ecx; lpEventAttributes
0x18002f274  call    cs:__imp_CreateEventExW
0x18002f27a  mov     [rbx+90h], rax
0x18002f281  test    rax, rax
0x18002f284  jnz     short loc_18002F28D
0x18002f286  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002f28b  jmp     short loc_18002F296
0x18002f28d  xor     eax, eax
0x18002f28f  jmp     short loc_18002F296
0x18002f291  mov     eax, 8007000Eh
0x18002f296  mov     rbx, [rsp+28h+arg_0]
0x18002f29b  mov     rsi, [rsp+28h+arg_8]
0x18002f2a0  add     rsp, 20h
0x18002f2a4  pop     rdi
0x18002f2a5  retn
```
