# LaunchLinkAction(HWND__ *,int)

- ea: `0x180007248`
- end: `0x18000729c`
- name: `?LaunchLinkAction@@YA_NPEAUHWND__@@H@Z`
- size: `84`
- prototype: `bool __fastcall(HWND, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006520`

## callees

- `0x1800071b4`
- `0x180007248`
- `0x180009d08`

## string_xrefs

- `0x180007290`: `http://go.microsoft.com/fwlink/?LinkId=21940`

## pseudocode

```c
char __fastcall LaunchLinkAction(HWND a1, int a2)
{
  int v2; // edx
  int v3; // edx
  int v4; // edx
  int v5; // edx
  OLECHAR *v7; // rdx

  v2 = a2 - 1244;
  if ( v2 )
  {
    v3 = v2 - 1;
    if ( !v3 )
      return LaunchCpl((const unsigned __int16 *)&stru_18000F860, 0);
    v4 = v3 - 2;
    if ( v4 )
    {
      v5 = v4 - 1;
      if ( v5 )
      {
        if ( v5 != 1 )
          return 1;
        v7 = L"windowsdefender://providers/";
      }
      else
      {
        v7 = L"windowsdefender://network/";
      }
    }
    else
    {
      v7 = L"windowsdefender://threat/";
    }
  }
  else
  {
    v7 = (OLECHAR *)L"http://go.microsoft.com/fwlink/?LinkId=21940";
  }
  return LaunchURL(a1, v7);
}

```

## disassembly

```asm
0x180007248  sub     edx, 4DCh
0x18000724e  jz      short loc_180007290
0x180007250  sub     edx, 1
0x180007253  jz      short loc_180007282
0x180007255  sub     edx, 2
0x180007258  jz      short loc_180007279
0x18000725a  sub     edx, 1
0x18000725d  jz      short loc_180007270
0x18000725f  cmp     edx, 1
0x180007262  jz      short loc_180007267
0x180007264  mov     al, 1
0x180007266  retn
0x180007267  lea     rdx, aWindowsdefende; "windowsdefender://providers/"
0x18000726e  jmp     short loc_180007297
0x180007270  lea     rdx, aWindowsdefende_0; "windowsdefender://network/"
0x180007277  jmp     short loc_180007297
0x180007279  lea     rdx, aWindowsdefende_1; "windowsdefender://threat/"
0x180007280  jmp     short loc_180007297
0x180007282  xor     edx, edx; unsigned __int16 *
0x180007284  lea     rcx, stru_18000F860; HWND
0x18000728b  jmp     ?LaunchCpl@@YA_NPEBG0@Z; LaunchCpl(ushort const *,ushort const *)
0x180007290  lea     rdx, aHttpGoMicrosof_2; "http://go.microsoft.com/fwlink/?LinkId="...
0x180007297  jmp     ?LaunchURL@@YA_NPEAUHWND__@@PEBG@Z; LaunchURL(HWND__ *,ushort const *)
```
