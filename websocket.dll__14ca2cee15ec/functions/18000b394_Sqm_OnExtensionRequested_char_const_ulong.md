# Sqm::OnExtensionRequested(char const *,ulong)

- ea: `0x18000b394`
- end: `0x18000b431`
- name: `?OnExtensionRequested@Sqm@@SAXPEBDK@Z`
- size: `157`
- prototype: `void __fastcall(const char *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800099e0`
- `0x18000aaf0`

## callees

- `0x18000b394`

## import_xrefs

- `ntdll!WinSqmIncrementDWORD` at `0x18000b420`
- `ntdll!WinSqmIncrementDWORD` at `0x18000b420`
- `ntdll!WinSqmIsOptedIn` at `0x18000b3ad`
- `ntdll!WinSqmIsOptedIn` at `0x18000b3ad`

## pseudocode

```c
void __fastcall Sqm::OnExtensionRequested(const char *a1, int a2)
{
  int IsOptedIn; // eax
  unsigned int v5; // ecx
  __int64 v6; // rdx
  char *v7; // r10
  char v8; // r8
  __int64 v9; // rdx

  if ( Sqm::initialized )
  {
    IsOptedIn = Sqm::enabled;
  }
  else
  {
    IsOptedIn = WinSqmIsOptedIn();
    Sqm::enabled = IsOptedIn;
    Sqm::initialized = 1;
  }
  if ( !IsOptedIn )
    return;
  v5 = 0;
  while ( 1 )
  {
    v6 = 0;
    v7 = (char *)*(&WebSocketExtensionSqmData + 2 * v5);
    v8 = *v7;
    if ( a2 )
    {
      while ( v8 == a1[v6] && v8 )
      {
        v6 = (unsigned int)(v6 + 1);
        v8 = v7[v6];
        if ( (_DWORD)v6 == a2 )
          goto LABEL_10;
      }
      goto LABEL_11;
    }
LABEL_10:
    if ( !v8 )
      break;
LABEL_11:
    if ( ++v5 >= 2 )
    {
      v9 = 9153;
      goto LABEL_14;
    }
  }
  v9 = *((unsigned int *)&WebSocketExtensionSqmData + 4 * v5 + 2);
LABEL_14:
  WinSqmIncrementDWORD(0, v9, 1);
}

```

## disassembly

```asm
0x18000b394  mov     [rsp+arg_0], rbx
0x18000b399  push    rdi
0x18000b39a  sub     rsp, 20h
0x18000b39e  mov     eax, cs:?initialized@Sqm@@0HC; int volatile Sqm::initialized
0x18000b3a4  mov     ebx, edx
0x18000b3a6  mov     rdi, rcx
0x18000b3a9  test    eax, eax
0x18000b3ab  jnz     short loc_18000B3C5
0x18000b3ad  call    cs:__imp_WinSqmIsOptedIn
0x18000b3b3  mov     cs:?enabled@Sqm@@0HA, eax; int Sqm::enabled
0x18000b3b9  mov     cs:?initialized@Sqm@@0HC, 1; int volatile Sqm::initialized
0x18000b3c3  jmp     short loc_18000B3CB
0x18000b3c5  mov     eax, cs:?enabled@Sqm@@0HA; int Sqm::enabled
0x18000b3cb  test    eax, eax
0x18000b3cd  jz      short loc_18000B426
0x18000b3cf  xor     ecx, ecx
0x18000b3d1  lea     r11, ?WebSocketExtensionSqmData@@3PAUWEBSOCKET_EXTENSION_SQM_DATA@@A; WEBSOCKET_EXTENSION_SQM_DATA near * WebSocketExtensionSqmData
0x18000b3d8  mov     r9d, ecx
0x18000b3db  xor     edx, edx
0x18000b3dd  add     r9, r9
0x18000b3e0  mov     r10, [r11+r9*8]
0x18000b3e4  mov     r8b, [r10]
0x18000b3e7  test    ebx, ebx
0x18000b3e9  jz      short loc_18000B400
0x18000b3eb  cmp     r8b, [rdx+rdi]
0x18000b3ef  jnz     short loc_18000B405
0x18000b3f1  test    r8b, r8b
0x18000b3f4  jz      short loc_18000B405
0x18000b3f6  inc     edx
0x18000b3f8  mov     r8b, [rdx+r10]
0x18000b3fc  cmp     edx, ebx
0x18000b3fe  jnz     short loc_18000B3EB
0x18000b400  test    r8b, r8b
0x18000b403  jz      short loc_18000B413
0x18000b405  inc     ecx
0x18000b407  cmp     ecx, 2
0x18000b40a  jb      short loc_18000B3D8
0x18000b40c  mov     edx, 23C1h
0x18000b411  jmp     short loc_18000B418
0x18000b413  mov     edx, [r11+r9*8+8]
0x18000b418  mov     r8d, 1
0x18000b41e  xor     ecx, ecx
0x18000b420  call    cs:__imp_WinSqmIncrementDWORD
0x18000b426  mov     rbx, [rsp+28h+arg_0]
0x18000b42b  add     rsp, 20h
0x18000b42f  pop     rdi
0x18000b430  retn
```
